# Simple Notes App [![Visitors](https://api.visitorbadge.io/api/visitors?path=https%3A%2F%2Fgithub.com%2Fajitfawade%2Fdjango-notes-app&countColor=%232ccce4&style=plastic&labelStyle=upper)](https://visitorbadge.io/status?path=https%3A%2F%2Fgithub.com%2Fajitfawade%2Fdjango-notes-app)
This is a simple notes app built with React and Django.

## Requirements
1. Python 3.9
2. Node
3. React

## Installation
1. Clone the repository
```
git clone https://github.com/LondheShubham153/django-notes-app.git
```

2. Build the app
```
docker build -t notes-app .
```

3. Run the app
```
docker run -d -p 8000:8000 notes-app:latest
```

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`
`sudo apt install nginx`
