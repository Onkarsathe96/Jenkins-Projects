# Use full Python image to ensure C++ compilers for pandas are available
FROM python:3.9

# Standard environment variables for Python
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /app

# Upgrade pip and install requirements
RUN pip install --upgrade pip
COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

# Copy the entire project
COPY . /app/

# Expose the Django port
EXPOSE 8000

# Run the server on 0.0.0.0 (required for Docker)
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]