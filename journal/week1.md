# Week 1 — App Containerization


## Remember to Commit Your Code
Created a branch named Week 1 and merged into main branch

![image](https://user-images.githubusercontent.com/96145786/221734992-e104d2e0-e03d-4be7-ab40-f76d89922156.png)

### Actions

* Completed all steps during the livestream to containerize the application.
  * Reviewed notes and code in [Github - Week 1](https://github.com/omenking/aws-bootcamp-cruddur-2023/blob/week-1/journal/week1.md).
* Went through [video](https://youtu.be/k-_o0cCpksk) steps and added frontend and backend notifications functionality.
  * Documented notification endpoint for OpenAPI document.
  * Wrote Flask backend endpoint for notifications.
  * Wrote React page for notifications. 
* Went through [video](https://youtu.be/CbQNMaa6zTg) steps to set up PostgreSQL and DynamoDB Local
  * Ran DynamoDB Local container to ensure it worked
  * Ran Postgres container to ensure it worked  
  * [AWS Documentation - DynamoDB Local](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.DownloadingAndRunning.html)
  * [100 Days of Cloud - DynamoDB Local Challenge](https://github.com/100DaysofCloud/challenge-dynamodb-local)

  * Tested connecting to DynamoDB Local using ```aws dynamodb list-tables --endpoint-url http://localhost:8000``` which returned empty table info successfully.  I intentionally didn't add the Music tables.
 


  * Added steps to install PostgreSQL Client into [.gitpod.Dockerfile](../.gitpod.Dockerfile) and tested using ```psql -h localhost -p 5432 -U postgres -d postgres```

## Security Considerations
* Watched video.  Did not have time for additional activities on security considerations this week.
* Had seen that npm finds a lot of vulnerabilities, and normally you would want to fix these, but upgrading versions of dependencies could break the app.  We had a discussion about this in the Discord.

## Homework

### Added steps to update Gitpod environment 

As part of the setup to get the app to run locally in Python, we needed to ensure all the modules in requirements.txt are installed, as well as do an npm install before building the container, so it can copy the contents of node_modules.
Added the following to the .gitpod.yml init section to automate these steps whenever a new Gitpod workspace is spun up:

```
cd /workspace/aws-bootcamp-cruddur-2023/backend-flask
pip3 install -r requirements.txt
cd /workspace/aws-bootcamp-cruddur-2023/frontend-react-js
npm i
cd /workspace/aws-bootcamp-cruddur-2023/     
```

### Cleaned up DynamoDB Location for Local Environment

Rewatched the video for DynamoDB/Postgres and Andrew had done this as well (I found out afterwards).

### Rebuilt Docker containers using multi-stage to reduce size (in-progress).

Ran a ```docker compose build``` to do a build of the completed code.  Checking ```docker image ls```, we can see the sizes here:

```
REPOSITORY                                    TAG         IMAGE ID       CREATED              SIZE
aws-bootcamp-cruddur-2023-backend-flask       latest      xxxxxxxxx   5 seconds ago        129MB
aws-bootcamp-cruddur-2023-frontend-react-js   latest      xxxxxxxxx   11 minutes ago       1.19GB
postgres                                      13-alpine   xxxxxxxxx   13 days ago          238MB
amazon/dynamodb-local                         latest      xxxxxxxxx   3 weeks ago          499MB
```

* Ran a ```docker image prune -a``` to clear all stored images and start fresh.

* Added .dockerignore file to speed up build process and not send some files to Docker daemon.
* Created new Dockerfiles for Frontend and Backend called Dockerfile.prod to use multi-stage called Dockerfile.prod
* Created new docker-compose-prod file to trigger building multi-stage.

* Tested to ensure app starts properly and I can access frontend and backend.  Appears to work properly, didn't see any errors on startup.

## Publications

* [AWS Cloud Project Bootcamp – Week 1: Unofficial Homework Guide](https://www.linuxtek.ca/2023/02/18/aws-cloud-project-bootcamp-week-1-unofficial-homework-guide/)
* [Diving Deeper – Gitpod Cloud Development Environment](https://www.linuxtek.ca/2023/02/21/diving-deeper-gitpod-cloud-development-environment/)
