# demo

This is a simple Spring Boot demo project where I run two separate applications — `HelloApplication` and `WelcomeApplication` — in the same project using different ports and profiles.

- `HelloApplication` runs on port **8082**
- `WelcomeApplication` runs on port **8081**

---

## 📁 Project Structure

Both applications are located in the **same project**, and selected during execution by passing different:
- `mainClass`
- Spring profile (hello/welcome)

---

## 🧱 Prerequisites

Make sure you have:

- Java 17+ installed
- Maven installed and configured
- Git (optional, for version control)
- Internet connection (Maven will download dependencies)

---

## 🛠️ Step 1: Build the Project

First, compile and package your Spring Boot project using:

mvn clean install

clean: removes previous build files

install: compiles code, runs tests (if any), and installs the .jar to your local Maven repo

Run the Applications:

You can run either HelloApplication or WelcomeApplication using mvn spring-boot:run and specifying the main class and profile.
 1. Run Welcome Application (port 8081)

  cmd : mvn spring-boot:run \
  -Dspring-boot.run.mainClass=com.example.demo.WelcomeApplication \
  -Dspring-boot.run.profiles=welcome

  Explanation : 
  
  This runs WelcomeApplication.java

  Loads application-welcome.properties

  Starts server on port 8081

 2. Run Hello Application (port 8082)

    cmd - mvn spring-boot:run \
  -Dspring-boot.run.mainClass=com.example.demo.HelloApplication \
  -Dspring-boot.run.profiles=hello

  Explanation :
  
  This runs HelloApplication.java

  Loads application-hello.properties

  Starts server on port 8082


🌐  Access the Applications
Open your browser or use curl to test:

http://localhost:8081 → for Welcome app

http://localhost:8082 → for Hello app

📄 Configuration Files
    Spring Boot will load the appropriate .properties file based on the profile you pass:

src/main/resources/
├── application-hello.properties     # used by HelloApplication
└── application-welcome.properties   # used by WelcomeApplication

Each file defines its own server.port, so both apps can run together without conflict.


