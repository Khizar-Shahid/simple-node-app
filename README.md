# Simple Node.js Application

This is a simple Node.js application that demonstrates CI/CD using GitHub Actions and Jenkins.

## Prerequisites

- Node.js (v18.x or later)
- npm (comes with Node.js)
- Git
- Docker (for running Jenkins)

## Running the Application Locally

1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```
3. Run the application:
   ```bash
   npm start
   ```

## CI/CD Setup

### GitHub Actions
The application is configured with GitHub Actions. The workflow will automatically run on push to main branch and pull requests.

### Jenkins Setup
To run Jenkins using Docker:

```bash
docker run -d -p 8080:8080 -p 50000:50000 jenkins/jenkins:lts
```

After Jenkins is running:
1. Access Jenkins at http://localhost:8080
2. Get the initial admin password from the Docker logs
3. Install suggested plugins
4. Create a new Freestyle project
5. Configure Git repository
6. Add build step: Execute shell
7. Add the following commands in the shell:
   ```bash
   npm install
   npm start
   ``` 