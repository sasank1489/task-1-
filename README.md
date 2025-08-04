# 🚀 Node.js CI/CD Pipeline using GitHub Actions & Docker

This project demonstrates how to automate the deployment of a Node.js web application using **GitHub Actions** for CI/CD and **Docker** for containerization. It was completed as part of the DevOps Internship **Task 1**.

---

## 📌 Task Objective

**Automate Code Deployment Using CI/CD Pipeline**

> Set up a CI/CD pipeline to build and deploy a web app using GitHub Actions. The pipeline should:
> - Build the app  
> - Run tests  
> - Build a Docker image  
> - Push the Docker image to DockerHub  

---

## 🧰 Tech Stack

| Tool           | Purpose                               |
|----------------|----------------------------------------|
| Node.js        | Backend web framework (Express.js)     |
| Jest           | Testing the API routes                 |
| Docker         | Containerization and deployment        |
| GitHub Actions | Continuous Integration & Deployment    |
| DockerHub      | Hosting Docker images                  |

---

## 🗂 Project Structure

```
nodejs-ci-cd-app/
├── .github/workflows/main.yml   # GitHub Actions workflow
├── server.js                 # Express web server
├── tests/server.test.js      # API test using supertest + Jest
├── Dockerfile                # Docker image build instructions
├── package.json                  # Node.js dependencies & scripts
└── README.md                     # This documentation
```

---

## ⚙️ How It Works

### GitHub Actions CI/CD Pipeline

The workflow is defined in `.github/workflows/ci-cd.yml`.

1. **Trigger**: On every push to the `main` branch  
2. **Actions**:
   - Checkout the code  
   - Set up Node.js environment  
   - Install dependencies  
   - Run Jest tests  
   - Build a Docker image  
   - Log in to DockerHub  
   - Push the Docker image  

---

## 🔧 How to Run Locally

1. Clone the repository:

```bash
git clone https://github.com/yourusername/nodejs-ci-cd-app.git
cd nodejs-ci-cd-app
```

2. Install dependencies:

```bash
npm install
```

3. Run the server:

```bash
npm start
```

4. Run tests:

```bash
npm test
```

---

## 🐳 Docker Commands

### Build Docker Image

```bash
docker build -t nodejs-ci-cd-app .
```

### Run Container

```bash
docker run -p 3000:3000 nodejs-ci-cd-app
```

---

## 🔐 GitHub Secrets Required

To push the image to DockerHub, configure the following secrets in your GitHub repository:

- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`

---

## ✅ Sample Output

### 🖼 Workflow Success Screenshot
<img width="990" height="364" alt="image" src="https://github.com/user-attachments/assets/b17392f9-af37-4be6-8b27-b1eb8576cf85" />

---

## 📊 API Endpoints

| Route     | Method | Description                  |
|-----------|--------|------------------------------|
| `/`       | GET    | Returns a welcome message     |
| `/status` | GET    | Returns `{ status: 'OK' }`    |

---

## 🧪 Test Details

Testing is done using **Jest** and **Supertest**. The test case ensures the `/status` route works as expected.

```js
const request = require('supertest');
const app = require('../src/server');

describe('GET /status', () => {
  it('should return status OK', async () => {
    const response = await request(app).get('/status');
    expect(response.statusCode).toBe(200);
    expect(response.body).toEqual({ status: 'OK' });
  });
});
```

---

## 📦 DockerHub Repository

🔗 https://hub.docker.com/repository/docker/sasank1489/task1/general

---

## 📬 Submission

✅ Task completed and submitted for **DevOps Internship – Task 1**  
📅 Submission Date: *(Insert Date)*  
🔗 GitHub Repository: *(Insert Your Repo URL)*

---

## 🙋‍♂️ Author

- **Name:** sasank
- **GitHub:** [@sasank1489](https://github.com/task-1)  
- **Email:** sasank1489@gmail.com

---
