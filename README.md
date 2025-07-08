version: "3"
services:
  n8n:
    image: n8nio/n8n:latest
    restart: always
    ports:
      - "5678:5678"
    environment:
      - N8N_BASIC_AUTH_ACTIVE=true
      - N8N_BASIC_AUTH_USER=admin
      - N8N_BASIC_AUTH_PASSWORD=strongpassword123
      - N8N_HOST=0.0.0.0
      - N8N_PORT=5678
      - TZ=Asia/Karachi
    volumes:
      - ./n8n_data:/home/node/.n8n
services:
  - type: web
    name: n8n-tabdeeli
    env: docker
    branch: main
    dockerfilePath: ./docker-compose.yml
    instanceType: free
    plan: free
