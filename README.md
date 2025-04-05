# 🐳 Build and Test Dockerized Node.js App with GitHub Actions

## 🎯 Goal
Automatically **build a Docker image** and **run tests inside the container** every time code is pushed to the repository.

---

## ✅ Steps to Complete the Task

### 1. Create a Dockerfile 

- For **Node.js**, the Dockerfile might look like:

```Dockerfile
FROM node:18
WORKDIR /app
COPY package.json package-lock.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["node", "server.js"]
```

### 2. Create a GitHub Actions Workflow File
- Create .github/workflows/docker-ci.yml
#### This action will build the Docker image using your Dockerfile and run the command inside it (e.g., npm test or pytest).

 

### 3. Create Node.js Application

### 📌 Node.js App Setup


```bash
mkdir Dockerized_Nodejs && cd Dockerized_Nodejs
npm init -y
npm install express
npm install --save-dev jest supertest
```
Now, create some basic files:
1. server.js 
2. server.test.js 

![Alt Text](files.png)

And add the test script in package.json file as like this:

```bash
"scripts": {
  "start": "node index.js",
  "test": "jest"}

```
Here, **jest** use for **Node.js**


## 4. Push to GitHub Repository
After setting everything up, push the all code files to GitHub:
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/your-username/your-repo.git
git push -u origin main
```

## 3. CI/CD in Action
Every time anyone push code:

- Docker image is rebuilt

- App runs in a container

- Tests run inside the container

- Status is shown in GitHub Actions like this: 

  ![Alt Text](github_rslt.png)

This way, we can complete the Dokerized Nodejs Application using GitHub Actions.
