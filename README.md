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

Extract ZIP

text
Right click ZIP → "Extract All" 
OR
Double click ZIP → copy 2 folders inside
<img width="1320" height="322" alt="image" src="https://github.com/user-attachments/assets/30e52c28-dc43-4702-b771-f79dbce9f08d" />

Open Command Prompt/Terminal
cd Desktop/crud-dd-task-mean-app/backend
npm install
npm start

Navigate to `http://localhost:8081/`

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/ee2f5e79-6a3b-46b1-922f-ee6a859b5fa5" />
https://nodejs.org/en/download

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/b881ed83-c5df-432d-abf7-f8153978c1e4" />

<img width="940" height="229" alt="image" src="https://github.com/user-attachments/assets/e52d16b8-bdf3-46c2-b86f-b9ae3ca6aaf2" />
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\backend
npm install


<img width="940" height="435" alt="image" src="https://github.com/user-attachments/assets/fca1786f-bb3e-47d5-80f0-31b8bf625916" />
npm start
http://localhost:8080/

<img width="940" height="160" alt="image" src="https://github.com/user-attachments/assets/c3d8a1c8-28d5-479f-8034-01211e7add34" />

<img width="940" height="150" alt="image" src="https://github.com/user-attachments/assets/c81b475d-a48f-4c39-beab-64c9542b13c8" />
Frontend setup
1.	Open a new Command Prompt window (keep backend running).
2.	Run these commands:
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\frontend
npm install
npm start
Would you like to share pseudonymous usage data… (y/N)”
•	Type: N
•	Then press: Enter

<img width="940" height="265" alt="image" src="https://github.com/user-attachments/assets/bd8afff8-d574-43bf-a2b5-35e92a2d9c69" />
C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\frontend>npm start

<img width="940" height="424" alt="image" src="https://github.com/user-attachments/assets/770c02c7-057e-4c44-964d-0e18999fdf8f" />

<img width="940" height="261" alt="image" src="https://github.com/user-attachments/assets/364624bc-5bdf-44ff-9a1a-4e44e133d6c7" />
Create GitHub repo and push code

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/92762e04-636d-48f5-89e4-e8dfd5125a4f" />
3.	Connect local folder to repo
•	Open Command Prompt and run:
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app
git init
git remote add origin https://github.com/yourusername/discover-dollar-devops-task.git
git add .
git commit -m "Initial MEAN app setup"
git branch -M main
git push -u origin main

<img width="940" height="253" alt="image" src="https://github.com/user-attachments/assets/d1411879-2567-44f3-831b-6793e2cf7fc6" />

<img width="940" height="393" alt="image" src="https://github.com/user-attachments/assets/d1105840-4e3e-452c-a178-fdad89685397" />
 Backend Dockerfile
C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\backend

FROM node:18

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 8080

CMD ["npm", "start"]

<img width="940" height="360" alt="image" src="https://github.com/user-attachments/assets/e5169ffa-0cc9-4e6d-9c6d-c6c137baac56" />

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

<img width="940" height="372" alt="image" src="https://github.com/user-attachments/assets/78fdcc34-3363-4439-a6a8-73110ad0e006" />
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app
git add backend/Dockerfile frontend/Dockerfile
git commit -m "Add Dockerfiles for backend and frontend"
git push

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/8e5bb1be-c701-4ca8-a885-4e7fc55fcc08" />

Dockerfile is visible in backend and backend folder
build and test Docker images locally.
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\backend

https://www.docker.com/products/docker-desktop/

<img width="940" height="438" alt="image" src="https://github.com/user-attachments/assets/a91e6992-2255-4b46-b3ed-3128a46460c3" />

<img width="940" height="182" alt="image" src="https://github.com/user-attachments/assets/a00d6898-d831-49e9-9ef7-1290aa4541f0" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/1a779771-f12d-437f-b441-a2416288e8d4" />
Open Windows Start menu → type “PowerShell” → right-click “Windows PowerShell” → Run as administrator.

<img width="940" height="265" alt="image" src="https://github.com/user-attachments/assets/d39232f9-bbf2-4858-a29a-ece93efff276" />
it is done, restart your laptop (important).
1.	After restart, open Docker Desktop again.
•	The WSL warning should disappear.
•	Wait until bottom-left shows “Engine running”.

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/9715a0bf-5561-4938-b456-435d461df33d" />
docker info

<img width="940" height="474" alt="image" src="https://github.com/user-attachments/assets/4ee0817a-9b76-47de-b849-3275486036a4" />
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\backend
docker build -t dd-backend:latest .

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/40467a42-731f-4088-b284-54596d7b25ba" />
docker run -d -p 8080:8080 --name dd-backend dd-backend:latest

<img width="940" height="95" alt="image" src="https://github.com/user-attachments/assets/e331f32b-45cc-4962-abfb-556dd36acb9b" />
docker ps

<img width="940" height="152" alt="image" src="https://github.com/user-attachments/assets/06ff4958-d310-458f-98ed-78492796071e" />

<img width="940" height="205" alt="image" src="https://github.com/user-attachments/assets/b1bd3333-030c-46d9-9aea-bdf18b349ddb" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/9ff10226-4a3a-45b9-b0b5-8c151fee5be1" />
Dockerize frontend and test 
cd C:\Users\USER\Desktop\crud-dd-task-mean-app\crud-dd-task-mean-app\frontend
docker build -t dd-frontend:latest .

<img width="940" height="304" alt="image" src="https://github.com/user-attachments/assets/7887916f-af25-46e4-baa6-80431c919339" />
docker run -d -p 4200:80 --name dd-frontend dd-frontend:latest

<img width="940" height="115" alt="image" src="https://github.com/user-attachments/assets/0f6df8c1-4096-4c9f-a859-6941eb1a2664" />

<img width="940" height="476" alt="image" src="https://github.com/user-attachments/assets/c111541b-e4ee-4786-bcfe-04b5bba7b7ab" />

<img width="940" height="271" alt="image" src="https://github.com/user-attachments/assets/9f165df8-1ab6-41d9-9544-8f7b686e313d" />
1.	Create backend repo on Docker Hub
https://hub.docker.com/repositories
“Create repository”.

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/23193f89-b8fc-46a3-bb84-1cbc46935360" />
•	Repository name: dd-backend
              dd-frontend
Now push from terminal
docker login
docker push dpraveenpaw/dd-backend:latest
docker push dpraveenpaw/dd-frontend:latest
Refresh Docker Hub 

docker login

<img width="940" height="223" alt="image" src="https://github.com/user-attachments/assets/bb1401da-e390-49ca-ae50-657ba773c331" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/3ad8f457-2f26-400c-9de8-41cf83a7893c" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/38b7b5ac-9374-4d06-b659-38f5749d24dd" />
docker push dpraveenpaw/dd-backend:latest

<img width="940" height="413" alt="image" src="https://github.com/user-attachments/assets/f8fe5086-5058-4ee3-92d7-3b0d595fe995" />

<img width="940" height="253" alt="image" src="https://github.com/user-attachments/assets/9a8d36c9-f6b3-4213-872a-e17b04a1b3ce" />
 
docker push dpraveenpaw/dd-frontend:latest



<img width="940" height="223" alt="image" src="https://github.com/user-attachments/assets/98d93fd0-841d-4f26-be34-001e7f5ae1d3" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/4cadf65a-d19a-4ea8-bcde-c62413528223" />

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/b2587ab7-1f62-40ac-a642-e61bb77064f8" />
•	AWS console → EC2 → Launch instance.
•	Name: dd-devops-task.
•	AMI: Ubuntu Server 22.04 LTS (free tier).
•	Instance type: t2.micro (for testing).
•	Key pair: create/download .pem.
•	Security group inbound rules:
•	SSH: TCP 22 from My IP.
•	HTTP: TCP 80 from 0.0.0.0/0.

<img width="940" height="1038" alt="image" src="https://github.com/user-attachments/assets/ba83c393-0d19-4d2f-8477-c744a7cbd2db" />
sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin
sudo usermod -aG docker ubuntu
exit

<img width="940" height="307" alt="image" src="https://github.com/user-attachments/assets/1380bc45-644e-41a8-a499-8b043d0f1f06" />
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

<img width="940" height="219" alt="image" src="https://github.com/user-attachments/assets/3d5b09ca-dbdd-484b-a2a0-ed782884c299" />
docker compose pull

<img width="940" height="166" alt="image" src="https://github.com/user-attachments/assets/cc01a2ff-fdff-4b05-a5bd-cf1c63075c3d" />
docker compose up -d

<img width="940" height="180" alt="image" src="https://github.com/user-attachments/assets/4a23a825-5208-4070-8e12-390ef8e15b95" />

<img width="940" height="186" alt="image" src="https://github.com/user-attachments/assets/8f9d58b4-5565-4aad-b3fd-a684cc2307b1" />
•	http://EC2_PUBLIC_IP/ → should show DD Task UI.
•	http://EC2_PUBLIC_IP:8080/ → should show JSON welcome.

<img width="940" height="228" alt="image" src="https://github.com/user-attachments/assets/61470d8f-dbde-4ca4-b6e2-5a64a62e2d03" />

<img width="940" height="148" alt="image" src="https://github.com/user-attachments/assets/d1dc691f-ae88-46e6-a340-c21cc4668051" />

Go to your project repository page

<img width="940" height="208" alt="image" src="https://github.com/user-attachments/assets/4256bd64-5201-4f55-b5ac-3f770af899af" />
At top, click the Settings tab of that repo
1.	Left side menu in repo settings → expand Security if needed → click Secrets and variables → Actions.

<img width="940" height="382" alt="image" src="https://github.com/user-attachments/assets/c8eb547c-ac88-43c7-a382-151f5ac565da" />

For the docker the token 
DOCKERHUB_TOKEN = Docker Hub personal access token create from Docker Hub → Account settings → Personal access tokens → Read, Write

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/00ef2cad-e639-4c57-a3b1-cc2d6bee2e59" />
And if you have the ppk need to convert  by using the putty gen

<img width="940" height="148" alt="image" src="https://github.com/user-attachments/assets/8072c5a1-0a79-4a98-be0e-42c4965d4630" />
GitHub Actions  (ubuntu) must be in the docker group 
sudo usermod -aG docker ubuntu
sudo chmod 666 /var/run/docker.sock

<img width="940" height="239" alt="image" src="https://github.com/user-attachments/assets/5d6bf9b7-8982-43af-85ec-cb8d7fdf2777" />
groups ubuntu
docker ps
Create workflow file locally
In your project root (same folder as backend, frontend, README)
mkdir -p .github/workflows
the code need to add in the above dir .github/workflows/cicd.yml
the file name is cicd.yml

<img width="940" height="188" alt="image" src="https://github.com/user-attachments/assets/3e75b6dd-8749-4241-b187-10e282411bc7" />
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

<img width="940" height="248" alt="image" src="https://github.com/user-attachments/assets/104a4a86-25a4-4858-9273-059e820113f9" />
Check run

<img width="940" height="240" alt="image" src="https://github.com/user-attachments/assets/a8b05500-2649-4032-9937-843572b81368" />
repo → Actions tab → open the latest run of “CI/CD - Build, Push and Deploy
On every push to main, GitHub Actions will:
•	Build backend and frontend Docker images.
•	Push them to Docker Hub (dpraveenpaw/dd-backend:latest, dpraveenpaw/dd-frontend:latest).github+1
•	SSH into EC2 as ubuntu and run cd dd-task && docker compose pull && docker compose up -d, updating the running containers automatically

D PRAVEEN
D.PRAVEEN4YOU@GMAIL.COM
