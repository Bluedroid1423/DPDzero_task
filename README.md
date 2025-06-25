# 🚀 DevOps Task – NGINX Reverse Proxy + Docker Microservices

This project demonstrates a simple microservices architecture using Docker and Docker Compose. It includes:

- Two services:  
  - A **Go-based backend service**  
  - A **Python Flask API service**  
- An **NGINX reverse proxy** for routing requests to the respective services

---

## 📁 Project Structure

```
DevOps_task/
├── docker-compose.yml
├── nginx/
│   ├── Dockerfile
│   └── nginx.conf
├── service_1/
│   ├── Dockerfile
│   └── main.go
├── service_2/
│   ├── Dockerfile
│   └── app.py
└── README.md
```

---

## ⚙️ Technologies Used

- Docker
- Docker Compose
- NGINX (Reverse Proxy)
- Go (service_1)
- Python Flask (service_2)

---

## 🚀 How to Run the Project

### Prerequisites

- Docker installed
- Docker Compose installed

### Steps

```bash
# Clone the repository
git clone https://github.com/Bluedroid1423/DPDzero_task.git
cd DPDzero_task

# Build and run the containers
docker-compose up --build
```

---

## 🌐 Service Endpoints

- **NGINX Proxy**: http://localhost  
- **Go Service (service_1)**: http://localhost:8001  
- **Python Service (service_2)**: http://localhost:8002  

> NGINX forwards traffic to these services based on routing rules defined in `nginx/nginx.conf`.

---

## 🔧 Configuration Overview

### NGINX (`nginx/nginx.conf`)

Handles reverse proxying to both services:

```nginx
location /go {
    proxy_pass http://service_1:8001;
}
location /python {
    proxy_pass http://service_2:8002;
}
```

### Docker Compose (`docker-compose.yml`)

Defines the services and NGINX network, builds images, and manages container lifecycle.

---

## 🧪 Testing

Once running, test each endpoint in your browser or with `curl`:

```bash
curl http://localhost/go
curl http://localhost/python
```

---

## 📌 Notes

- Make sure ports `8001`, `8002`, and `80` are not in use before starting.
- You can modify service code and NGINX rules as per your requirements.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

## 🤝 Contributing

Feel free to fork this repo and submit pull requests.
