# Week 1 — App Containerization
In Week 1, I captured below details.
1. Basic Overview of Docker.
2. Configure a dyanmodb, postgres database locally and test the connectivity.
3. Configure front end and backend app.
4. Configure docker.

# Summary Report:
1. There are multiple CDE ( Cloud development environment) are there and a well articulated video by Chirag ( Link - https://www.youtube.com/watch?v=OAMHu1NiYoI) which explained CDE like Gitpod, cloudspace. This video covers the details on free tier and i am using Gitpod for my development.
2. Created a docker compose file for backend, frontend and databases ( Dyanmo DB and Postrges).
3. Install a postrgres client to test the connectivity.
4. Configure the backend notification page.

# My work

1. The docker compose file 

version: "3.8"
services:
  backend-flask:
    environment:
      FRONTEND_URL: "https://3000-${GITPOD_WORKSPACE_ID}.${GITPOD_WORKSPACE_CLUSTER_HOST}"
      BACKEND_URL: "https://4567-${GITPOD_WORKSPACE_ID}.${GITPOD_WORKSPACE_CLUSTER_HOST}"
    build: ./backend-flask
    ports:

    
      - "4567:4567"
    volumes:
      - ./backend-flask:/backend-flask
  frontend-react-js:
    environment:
      REACT_APP_BACKEND_URL: "https://4567-${GITPOD_WORKSPACE_ID}.${GITPOD_WORKSPACE_CLUSTER_HOST}"
    build: ./frontend-react-js
    ports:
      - "3000:3000"
    volumes:
      - ./frontend-react-js:/frontend-react-js
      
   # The below section is for the database
  db:
    image: postgres:13-alpine
    restart: always
    environment:
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=password
    ports:
      - '5432:5432'
    volumes: 
      - db:/var/lib/postgresql/data**
  dynamodb-local:
    user: root
    command: "-jar DynamoDBLocal.jar -sharedDb -dbPath ./data"
    image: "amazon/dynamodb-local:latest"
    container_name: dynamodb-local
    ports:
      - "8000:8000"
    volumes:
      - "./docker/dynamodb:/home/dynamodblocal/data"
    working_dir: /home/dynamodblocal
volumes:
  db:
    driver: local
# the name flag is a hack to change the default prepend folder
# name when outputting the image names
networks: 
  internal-network:
    driver: bridge
    name: cruddur

2. After configuring back end and front end notification as per Andrew's video ( Link - https://www.youtube.com/watch?v=k-_o0cCpksk) I am able to access my front end.
<img width="865" alt="image" src="https://user-images.githubusercontent.com/24868114/221369384-ad027688-dce2-4d96-b960-30dd54db6dfd.png">


3. I configured the postgres client in my gitpod.yml file so that everytime when i will do the docker compose, the client will automatically added.

tasks:
  - name: aws-cli
    env:
      AWS_CLI_AUTO_PROMPT: on-partial
    init: |
      cd /workspace 
      curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
      unzip awscliv2.zip
      sudo ./aws/install
      cd $THEIA_WORKSPACE_ROOT
        - name: postgres
      curl -fsSL https://www.postgresql.org/media/keys/ACCC4CF8.asc|sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/postgresql.gpg
      echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" |sudo tee  /etc/apt/sources.list.d/pgdg.list
      sudo apt update
      sudo apt install -y postgresql-client-13 libpq-dev
      cd frontend-react-js
      npm i
      cd ../
vscode:
  extensions:
    - 42Crunch.vscode-openapi
    - cweijan.vscode-postgresql-client2
4. Test the postgres connectivity and it is working as expected.
<img width="592" alt="image" src="https://user-images.githubusercontent.com/24868114/221369411-c8697ef5-233b-4d38-9303-80750d8e739a.png">





