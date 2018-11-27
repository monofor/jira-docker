Create your persistent volume

```sh
docker volume create your-jira
```

Run your image

```sh
docker run -d \
    -v your-jira:/var/atlassian/jira \
    -p 80:8080 --name your-jira-container \
    -e X_PROXY_NAME=subdomain.yourdomain.com \
    -e X_PROXY_PORT=443 \
    -e X_PROXY_SCHEME=https \
    --restart=always \
    cptactionhank/atlassian-jira-software:latest
```