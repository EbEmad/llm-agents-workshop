# Use official Python image
FROM python:3.12-slim

WORKDIR /app

# Prevent Python from writing .pyc files and buffer logs
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
COPY requirements.txt .
RUN pip install uv
# Install dependencies
RUN uv pip install -r requirements.txt --system

# Copy the rest of the application code
COPY work.ipynb .

# Expose the port Jupyter will run on
EXPOSE 8888

# Set default command to start Jupyter Notebook
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
