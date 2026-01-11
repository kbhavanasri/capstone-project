# -------- Build Stage --------
FROM python:3.11-slim AS builder

WORKDIR /app
COPY requirements.txt .
RUN pip install --user --no-cache-dir -r requirements.txt

# -------- Runtime Stage --------
FROM python:3.11-slim

# Create non-root user
RUN useradd -m appuser

# Set working directory
WORKDIR /app

# Copy only the Python packages installed for the user
COPY --from=builder /root/.local /root/.local

# Add local python packages to PATH
ENV PATH=/root/.local/bin:$PATH

# Copy application code
COPY app.py .

# Switch to non-root user
USER appuser

EXPOSE 5000

# Run the application
CMD ["python", "app.py"]
