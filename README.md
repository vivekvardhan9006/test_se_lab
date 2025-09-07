# Food System - Restaurant Management

A comprehensive web-based Restaurant Management System built with Java, JSP, and Maven, containerized with Docker and Tomcat.

## Project Overview

This project is a web-based Food System that provides a complete solution for managing restaurant operations including menu management, order processing, customer management, and analytics. The application is built using Java web technologies and deployed using Docker with Apache Tomcat.

## Features

- **🍕 Menu Management**: Create, update, and manage restaurant menus with categories and pricing
- **📋 Order Processing**: Streamlined order management from kitchen to customer table
- **👥 Customer Management**: Customer profiles, preferences, and loyalty programs
- **📊 Analytics & Reports**: Comprehensive reporting on sales and business trends
- **🌐 Web-based Interface**: Modern, responsive JSP-based user interface
- **🐳 Docker Containerization**: Easy deployment and scaling
- **⚙️ Maven Build System**: Automated dependency management and building
- **🚀 Tomcat Integration**: Production-ready web server deployment

## Technology Stack

- **Backend**: Java 11
- **Frontend**: JSP, HTML5, CSS3, JavaScript
- **Build Tool**: Maven 3.6+
- **Web Server**: Apache Tomcat 9.0
- **Containerization**: Docker, Docker Compose
- **Testing**: JUnit 4.13.2

## Prerequisites

- Java 11 or higher
- Maven 3.6 or higher
- Docker Desktop
- Docker Compose

## Project Structure

```
FoodSystem/
├── src/
│   └── main/
│       └── webapp/
│           ├── index.jsp
│           └── WEB-INF/
│               └── web.xml
├── target/
│   └── FoodSystem.war
├── pom.xml
├── Dockerfile
├── docker-compose.yml
├── .dockerignore
└── README.md
```

## Quick Start

### Using Docker Compose (Recommended)

1. **Build and run the application:**
   ```bash
   docker-compose up --build
   ```

2. **Run in detached mode:**
   ```bash
   docker-compose up -d --build
   ```

3. **Stop the application:**
   ```bash
   docker-compose down
   ```

4. **View logs:**
   ```bash
   docker-compose logs -f
   ```

### Using Docker Commands

1. **Build the Maven project:**
   ```bash
   mvn clean package
   ```

2. **Build the Docker image:**
   ```bash
   docker build -t food-system .
   ```

3. **Run the container:**
   ```bash
   docker run -p 8080:8080 food-system
   ```

4. **Run in detached mode:**
   ```bash
   docker run -d -p 8080:8080 food-system
   ```

## Accessing the Application

Once the container is running, access the application at:
- **URL**: http://localhost:8080/FoodSystem
- **Port**: 8080

## Configuration

### Maven Configuration

The project includes proper Maven configuration with:
- **Packaging**: WAR (Web Archive)
- **Java Version**: 11
- **Compiler Plugin**: Maven Compiler Plugin 3.11.0
- **War Plugin**: Maven War Plugin 3.2.3
- **Testing**: JUnit 4.13.2

### Docker Configuration

- **Base Image**: tomcat:9.0-jdk11-openjdk-slim
- **Port**: 8080
- **Deployment**: WAR file deployed to Tomcat webapps directory
- **Command**: catalina.sh run

### Docker Compose Configuration

- **Service Name**: food-system
- **Container Name**: food-system-app
- **Port Mapping**: 8080:8080
- **Restart Policy**: unless-stopped
- **Network**: food-network
- **Health Check**: Built-in health monitoring

## Development

### Building the Project

```bash
# Clean and compile
mvn clean compile

# Run tests
mvn test

# Package the application
mvn clean package

# Install dependencies
mvn install
```

### Running Tests

```bash
mvn test
```

### Local Development

1. **Start Tomcat locally:**
   ```bash
   # Deploy the WAR file to your local Tomcat installation
   cp target/FoodSystem.war $TOMCAT_HOME/webapps/
   ```

2. **Access the application:**
   - Navigate to http://localhost:8080/FoodSystem

## API Endpoints

The application currently provides:

- **Home Page**: `/FoodSystem/` - Main dashboard with restaurant management features
- **Welcome Page**: Displays food system features and statistics

## Restaurant Management Features

### 🍕 Menu Management
- Create and manage menu categories
- Add, edit, and remove menu items
- Set pricing and descriptions
- Manage availability and seasonal items

### 📋 Order Processing
- Real-time order tracking
- Kitchen order management
- Table assignment and service
- Order status updates

### 👥 Customer Management
- Customer registration and profiles
- Order history tracking
- Loyalty program management
- Customer preferences and dietary restrictions

### 📊 Analytics & Reports
- Daily, weekly, and monthly sales reports
- Popular menu item analytics
- Peak hour analysis
- Revenue trend tracking
- Customer satisfaction metrics

## Troubleshooting

### Common Issues

1. **Port already in use:**
   ```bash
   # Check what's using port 8080
   netstat -ano | findstr :8080
   
   # Kill the process or use a different port
   docker run -p 8081:8080 food-system
   ```

2. **Docker build fails:**
   - Ensure Docker Desktop is running
   - Check if Maven build was successful: `mvn clean package`
   - Verify WAR file exists in target directory

3. **Application not accessible:**
   - Check container status: `docker ps`
   - View container logs: `docker logs <container_id>`
   - Verify port mapping: `docker port <container_id>`

4. **Maven build issues:**
   - Clean and rebuild: `mvn clean package`
   - Check Java version: `java -version`
   - Verify Maven installation: `mvn -version`

### Docker Commands

```bash
# List running containers
docker ps

# View container logs
docker logs <container_id>

# Stop container
docker stop <container_id>

# Remove container
docker rm <container_id>

# Remove image
docker rmi food-system

# Clean up unused resources
docker system prune
```

## Deployment

### Production Deployment

1. **Build production image:**
   ```bash
   docker build -t food-system:latest .
   ```

2. **Deploy with Docker Compose:**
   ```bash
   docker-compose up -d
   ```

3. **Scale the application:**
   ```bash
   docker-compose up -d --scale food-system=3
   ```

### Environment Variables

The application supports the following environment variables:
- `TZ`: Timezone (default: UTC)
- `JAVA_OPTS`: Additional JVM options (default: -Xmx512m -Xms256m)

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Future Enhancements

- [ ] Database integration (MySQL/PostgreSQL)
- [ ] User authentication and authorization
- [ ] REST API endpoints for mobile apps
- [ ] Real-time order tracking
- [ ] Payment gateway integration
- [ ] Inventory management system
- [ ] Staff management and scheduling
- [ ] Customer mobile app
- [ ] Advanced analytics dashboard
- [ ] Multi-location support

## Business Benefits

- **Increased Efficiency**: Streamlined order processing and kitchen management
- **Better Customer Experience**: Faster service and order accuracy
- **Data-Driven Decisions**: Comprehensive analytics and reporting
- **Cost Reduction**: Automated processes and better inventory management
- **Scalability**: Easy to expand to multiple locations

## License

This project is for educational purposes as part of a software engineering course.

## Contact

For questions or support, please contact the development team.

---

**Note**: This is a foundational web application that demonstrates proper Java web development practices, Maven configuration, and Docker containerization. It serves as a starting point for building a comprehensive restaurant management system.
