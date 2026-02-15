# Base image (OS)
FROM python:3.7

# Working directory
WORKDIR /app

# Copy src code to container
COPY . .

# Run the build commands [to install libraries]
RUN pip install -r requirements.txt

# serve the app / run the app (keep it running)
CMD ["python","app.py"]





