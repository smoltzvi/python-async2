# Use the official lightweight Python image.
# https://hub.docker.com/_/python
FROM python:3.11-slim

# Create environment variable
ENV APP_HOME /app
WORKDIR $APP_HOME
# Copy contents of current directory to working directory 
# Copy local code to the container image
COPY . ./

# Install production dependencies.
RUN pip install google-cloud-storage

# Set up authentication credentials
ENV GOOGLE_APPLICATION_CREDENTIALS=$APP_HOME/sandbox-io-289003-1138a13c78c9.json
# docker run --name my-py-container -v C:\Users\Smoltz\projects\python-async\app\sandbox-io-289003-1138a13c78c9.json:/app my-py-app

# Run the app on container startup.
# Give bucket a name.
CMD ["python", "storage_async_upload.py", "kimobucket"]