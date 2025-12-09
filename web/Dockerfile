FROM python:3.11-slim

WORKDIR /app

# Install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY . .

# Default port (for local/Droplet); App Platform will override PORT env
ENV PORT=8000

# Run the application
# Use *shell form* so ${PORT} is expanded from the environment
CMD gunicorn --bind "0.0.0.0:${PORT}" --workers 4 "app:create_app()"
