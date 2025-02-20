# softeng-microservices-flask

###### 🛠️ Deployment Instructions ######

-**Prerequisites**
Ensure you have the following installed

## Docker: Install Docker
## Docker Compose: Install Docker Compose

-**Steps to Deploy**
1. Clone the Repository

git clone https://github.com/your-repository/your-project.git
cd your-project

2. Create an Environment File

cp .env.example .env

Update the .env file with your database credentials.

3. Build and Start the Containers

docker-compose up --build -d

This runs the services in detached mode (-d).

4. Check Running Containers

docker ps

5. Access the Services

User Service: http://localhost:5000

Order Service: http://localhost:5001

6. Stopping the Services

docker-compose down

This will stop and remove the containers.