
#!/bin/bash

# Update the system packages
sudo apt update -y

# Install Apache (httpd) web server
sudo apt install apache2 -y

# Enable Apache to start on boot
sudo systemctl enable apache2

# Start Apache service
sudo systemctl start apache2

# Check the status of Apache service
sudo systemctl status apache2

# Create a custom HTML page for testing
echo "<html><body><h1>WASTESTING GIT</h1></body></html>" | sudo tee /var/www/html/index.html

# Print the IP address to access the server
echo "Apache HTTP server installed and running."
echo "You can access your server at http://$(hostname -I | awk '{print $1}')/"
