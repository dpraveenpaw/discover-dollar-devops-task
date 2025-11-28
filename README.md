In this DevOps task, you need to build and deploy a full-stack CRUD application using the MEAN stack (MongoDB, Express, Angular 15, and Node.js). The backend will be developed with Node.js and Express to provide REST APIs, connecting to a MongoDB database. The frontend will be an Angular application utilizing HTTPClient for communication.  

The application will manage a collection of tutorials, where each tutorial includes an ID, title, description, and published status. Users will be able to create, retrieve, update, and delete tutorials. Additionally, a search box will allow users to find tutorials by title.

## Project setup

### Node.js Server

cd backend

npm install

You can update the MongoDB credentials by modifying the `db.config.js` file located in `app/config/`.

Run `node server.js`

### Angular Client

cd frontend

npm install

Run `ng serve --port 8081`

You can modify the `src/app/services/tutorial.service.ts` file to adjust how the frontend interacts with the backend.

Navigate to `http://localhost:8081/`


 
https://nodejs.org/en/download
 
 
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\backend
npm install
 
npm start
http://localhost:8080/
 
 Step 3: Frontend setup
1.	Open a new Command Prompt window (keep backend running).
2.	Run these commands:
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\frontend
npm install
npm start
Would you like to share pseudonymous usage data… (y/N)”
•	Type: N
•	Then press: Enter
 

C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\frontend>npm start

 
 
Create GitHub repo and push code
 
3.	Connect local folder to repo
•	Open Command Prompt and run:
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app
git init
git remote add origin https://github.com/yourusername/discover-dollar-devops-task.git
git add .
git commit -m "Initial MEAN app setup"
git branch -M main
git push -u origin main
 
 
 Backend Dockerfile
C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\backend

FROM node:18

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 8080

CMD ["npm", "start"]

 


Frontend Dockerfile
1.	C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\frontend

FROM node:18 AS build

WORKDIR /app
COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]



 

	
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app
git add backend/Dockerfile frontend/Dockerfile
git commit -m "Add Dockerfiles for backend and frontend"
git push
 
Dockerfile is visible in backend and backend folder
build and test Docker images locally.
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\backend

https://www.docker.com/products/docker-desktop/

 

 

 

Open Windows Start menu → type “PowerShell” → right-click “Windows PowerShell” → Run as administrator.
 
it is done, restart your laptop (important).
1.	After restart, open Docker Desktop again.
•	The WSL warning should disappear.
•	Wait until bottom-left shows “Engine running”.
 

docker info
 
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\backend
docker build -t dd-backend:latest .
 
docker run -d -p 8080:8080 --name dd-backend dd-backend:latest
 
docker ps
 
 
 

Dockerize frontend and test 
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\frontend
docker build -t dd-frontend:latest .
 

docker run -d -p 4200:80 --name dd-frontend dd-frontend:latest
 
 

 
1.	Create backend repo on Docker Hub
https://hub.docker.com/repositories
“Create repository”.
 
•	Repository name: dd-backend
              dd-frontend
Now push from terminal
docker login
docker push dpraveenpaw/dd-backend:latest
docker push dpraveenpaw/dd-frontend:latest
Refresh Docker Hub 

docker login
 

 
 
docker push dpraveenpaw/dd-backend:latest
 
 
docker push dpraveenpaw/dd-frontend:latest
 
 


 
•	AWS console → EC2 → Launch instance.
•	Name: dd-devops-task.
•	AMI: Ubuntu Server 22.04 LTS (free tier).
•	Instance type: t2.micro (for testing).
•	Key pair: create/download .pem.
•	Security group inbound rules:
•	SSH: TCP 22 from My IP.
•	HTTP: TCP 80 from 0.0.0.0/0.
 
sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin
sudo usermod -aG docker ubuntu
exit

 
Create docker-compose.yml on EC2
Still on EC2, in home directory:
ou should land in /home/ubuntu.
2. Install Docker + Compose
sudo apt-get update

sudo apt-get install -y \
  ca-certificates \
  curl \
  gnupg \
  lsb-release

sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
  sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin

docker --version
docker compose version
 
docker compose pull
 
docker compose up -d
 

 
•	http://EC2_PUBLIC_IP/ → should show DD Task UI.
•	http://EC2_PUBLIC_IP:8080/ → should show JSON welcome.
 

 
Go to your project repository page
 
At top, click the Settings tab of that repo
1.	Left side menu in repo settings → expand Security if needed → click Secrets and variables → Actions.
 
For the docker the token 
DOCKERHUB_TOKEN = Docker Hub personal access token create from Docker Hub → Account settings → Personal access tokens → Read, Write
 
And if you have the ppk need to convert  by using the putty gen
 


GitHub Actions  (ubuntu) must be in the docker group 
sudo usermod -aG docker ubuntu
sudo chmod 666 /var/run/docker.sock
 
groups ubuntu
docker ps
Create workflow file locally
In your project root (same folder as backend, frontend, README)
mkdir -p .github/workflows
the code need to add in the above dir .github/workflows/cicd.yml
the file name is cicd.yml
 
The file location and the .yml should be the code
name: CI/CD - Build, Push and Deploy

on:
  push:
    branches: [ main ]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Set up Docker Buildx
        uses: docker/setup-buildx-action@v3

      - name: Login to Docker Hub
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKERHUB_USERNAME }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}

      - name: Build and push backend image
        uses: docker/build-push-action@v6
        with:
          context: ./backend
          push: true
          tags: dpraveenpaw/dd-backend:latest

      - name: Build and push frontend image
        uses: docker/build-push-action@v6
        with:
          context: ./frontend
          push: true
          tags: dpraveenpaw/dd-frontend:latest

      - name: Deploy to EC2 via SSH
        uses: appleboy/ssh-action@v1.0.3
        with:
          host: ${{ secrets.EC2_HOST }}
          username: ${{ secrets.EC2_USER }}
          key: ${{ secrets.EC2_KEY }}
          script: |
            cd dd-task
            docker compose pull
            docker compose up -d

the indentation is important 
2) Commit and push
git add .github/workflows/cicd.yml
git commit -m "Add CI/CD workflow for Docker and EC2 deploy"
git push
 
Check run
 
repo → Actions tab → open the latest run of “CI/CD - Build, Push and Deploy
On every push to main, GitHub Actions will:
•	Build backend and frontend Docker images.
•	Push them to Docker Hub (dpraveenpaw/dd-backend:latest, dpraveenpaw/dd-frontend:latest).github+1
•	SSH into EC2 as ubuntu and run cd dd-task && docker compose pull && docker compose up -d, updating the running containers automatically
 

