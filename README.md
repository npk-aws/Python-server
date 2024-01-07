# Python-server
Creating a basic Python web server, containerizing it with Docker, and hosting it on an Amazon EC2 instance.

Step 1: Creating a Basic Python Web Server                                                          
Create a file named app.py with the necessary content

Step 2: Creating a Docker Container                                                                                 
Create a file named Dockerfile with the necessary content

Step 3: Build and Run the Docker Container Locally                                                           
Open a terminal, in the directory containing both app.py and Dockerfile, run the following commands:
# Build the Docker image
docker build -t python-web-server .

# Run the Docker container
docker run -p 8000:8000 python-web-server

Visit http://localhost:8000 in your web browser to see the "Hello, World!" message.

Step 4: Host on Amazon EC2
Create an EC2 instance 

1. Transfer Files to EC2:

Use scp (Secure Copy Protocol) to transfer files to the EC2 instance. Replace EC2_PUBLIC_IP with the EC2 instance's public IP address.

scp -i path/to/your/key.pem app.py Dockerfile user@EC2_PUBLIC_IP:/path/on/ec2

2. Connect to EC2:

Connect to the EC2 instance using SSH. Replace EC2_PUBLIC_IP and path/to/key.pem with the EC2 instance's public IP address and the path to the private key.

ssh -i path/to/key.pem user@EC2_PUBLIC_IP

3. Build and Run Docker Container on EC2:

On the EC2 instance, navigate to the directory where you transferred the files and run the following commands:
# Build the Docker image
docker build -t python-web-server .

# Run the Docker container in detached mode
docker run -d -p 80:8000 python-web-server

4. Access the Web Server:

Open the web browser and enter the EC2 instance's public IP address. We should see the "Hello, World!" message.




