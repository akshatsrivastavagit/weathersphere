![weathersphereprothumbnail](https://github.com/user-attachments/assets/5d4606a1-d528-46ca-9dfe-28d823dee3e8)



# WeatherSphere - Weather Application

WeatherSphere is a modern, single-page weather application that provides real-time weather information for any location worldwide. The application features a user-friendly interface with location search functionality and detailed weather forecasts.

## Features

- 🔍 Location search with autocomplete suggestions
- 📍 Current location detection
- 🌡️ Real-time weather information
- 📊 24-hour weather forecast
- 📅 5-day weather forecast
- 🌤️ Detailed weather conditions including temperature, humidity, wind speed, etc.

## Technologies Used

- HTML5
- CSS3
- JavaScript
- Weather API Integration
- Docker
- Jenkins CI/CD
- Cloudflare
- GitHub

## Project Structure

The project consists of a single-page application (`index.html`) that contains:
- HTML structure
- CSS styling
- JavaScript functionality
- Weather API integration

## Deployment Pipeline

The project uses a CI/CD pipeline with the following components:

1. **GitHub Repository**: Hosts the source code
2. **Cloudflare**: Monitors GitHub for changes and triggers Jenkins builds
3. **Jenkins Pipeline**: Automates the build and deployment process
4. **Docker**: Containerizes the application
5. **Docker Hub**: Stores the container images

### Jenkins Pipeline Stages

1. **Clone Repository**: Fetches the latest code from GitHub
2. **Build Docker Image**: Creates a Docker image of the application
3. **Stop Previous Container**: Ensures clean deployment
4. **Run Docker Container**: Deploys the application on a specified port
5. **Push to Docker Hub**: Stores the latest image in Docker Hub

## Getting Started

### Prerequisites

- Docker
- Jenkins
- Cloudflare account
- Docker Hub account

### Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/akgithubgre/weathersphere.git
   ```

2. Open `index.html` in your web browser to run the application locally

### Deployment

The application is automatically deployed when changes are pushed to the main branch. The deployment process includes:

1. Code push to GitHub
2. Cloudflare webhook trigger
3. Jenkins pipeline execution
4. Docker container deployment
5. Email notification of build status

## Build Status

The Jenkins pipeline sends email notifications for:
- ✅ Successful builds
- ❌ Failed builds

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

For any queries or support, please reach out to the project maintainer.
