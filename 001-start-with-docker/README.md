# 001 Run docker container

Run container with HTTP server that serves simple HTML page

## 1. Run nginx server docker image

1. Run command `docker run -p 8080:80 nginx`
2. Navigate to http://localhost:8080

## 2. Use nginx container to serve your HTML page

1. Create simple html page named `index.html`
2. Run command `docker run -p 8080:80 -v $PWD:/usr/share/nginx/html:ro nginx`
3. Navigate to http://localhost:8080


## 3. Build httpd container with your web page

1. Create `Dockerfile` as below
2. Build named docker image: `docker build -t docker101-httpd .`
3. Run container: `docker run -p 8080:80 docker101-httpd`
4. Navigate to http://localhost:8080
5. Try to navigate to http://localhost:8080/README.md (hint: `.dockerignore` file)


Dockerfile: 

```
FROM nginx
COPY . /usr/share/nginx/html
```

