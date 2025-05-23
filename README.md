# WeatherSphere - Weather Application

![WeatherSphere Thumbnail](https://github.com/user-attachments/assets/5d4606a1-d528-46ca-9dfe-28d823dee3e8)

WeatherSphere is a modern, single-page weather application that provides real-time weather information for any location worldwide. The application features a user-friendly interface with location search functionality and detailed weather forecasts.

---

## 🚀 Features

- 🔍 Location search with autocomplete suggestions  
- 📍 Current location detection  
- 🌡️ Real-time weather information  
- 📊 24-hour weather forecast  
- 📅 5-day weather forecast  
- 🌤️ Detailed weather conditions including temperature, humidity, wind speed, and more  

---

## 🛠️ Technologies Used

- HTML5  
- CSS3  
- JavaScript  
- Weather API Integration  
- Docker  
- Jenkins CI/CD  
- Cloudflare  
- GitHub  

---

## 🗂️ Project Structure

The project is a single-page application consisting of:

- `index.html` - Markup structure  
- `style.css` - Styling  
- `app.js` - Functionality and API calls  
- Dockerfile - For containerization  

---

## ⚙️ Deployment Pipeline

WeatherSphere is deployed using a modern DevOps pipeline:

### 🔧 Tools & Platforms

- **GitHub** – Source code repository  
- **Cloudflare** – Webhook triggers Jenkins on code push  
- **Jenkins** – Automates build and deployment  
- **Docker** – Containerizes the application  
- **Docker Hub** – Hosts built images  

### 📦 Jenkins Pipeline Stages

1. **Clone Repository**: Fetch latest code from GitHub  
2. **Build Docker Image**: Create Docker image  
3. **Stop Previous Container**: Ensure clean slate  
4. **Run Docker Container**: Deploy on specified port  
5. **Push to Docker Hub**: Store new image  

---

## 🖼️ Screenshots

### 🌐 Homepage of Application
*User-facing weather dashboard.*

![image](https://github.com/user-attachments/assets/d5879f49-95bf-425e-a05c-0431a7a79cc5)


---

### 🔧 System Design Flow

![image](https://github.com/user-attachments/assets/e31e8a10-bb64-4e5c-8945-e62791620519)


---

### 🧪 Jenkins Dashboard - Successful Build
*Visual confirmation of Jenkins build success.*

![image](https://github.com/user-attachments/assets/cb162bc1-09ca-407b-9ee7-237aba58d915)


---

### 🔄 Jenkins Build Pipeline
*Stages of the CI/CD pipeline.*

![image](https://github.com/user-attachments/assets/df98db8b-add3-4021-a3e1-fdf891dc055c)


---

### 🖥️ Jenkins Terminal Output
*Logs from Jenkins during build.*

![image](https://github.com/user-attachments/assets/cc39a632-15c8-4373-9282-4f7d54ab6f06)


---

### 📬 Deployment Email Notification
*Email alert for successful deployment.*

![image](https://github.com/user-attachments/assets/3e5674c3-ae87-4d26-95bd-c2db202b80d8)


---

### 🖥️ Cloudflare Running (CMD)
*Terminal showing Cloudflare CLI status.*

![image](https://github.com/user-attachments/assets/5ebf855d-f025-47c6-aec8-73cea6ade15f)


---

## 🧪 Getting Started

### Prerequisites

- Docker  
- Jenkins  
- Cloudflare account  
- Docker Hub account  

---

### 💻 Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/akgithubgre/weathersphere.git
   ```

2. Open `index.html` in your web browser to view locally.

---

### 🚀 Deployment Flow

1. Code pushed to GitHub  
2. Cloudflare triggers Jenkins via webhook  
3. Jenkins builds and deploys Docker container  
4. Latest image is pushed to Docker Hub  
5. Email notification sent on build success/failure  

---

## 📬 Build Status Notifications

Jenkins sends email updates for:
- ✅ Successful builds  
- ❌ Failed builds  

---

## 🤝 Contributing

1. Fork the repository  
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)  
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)  
4. Push to the branch (`git push origin feature/AmazingFeature`)  
5. Open a Pull Request  


---

## 📬 Contact

For queries or support, please reach out to the project maintainer.

---

