# DHIS2 Installation Guide on Ubuntu on Windows (WSL)

This guide provides a step-by-step process for installing **DHIS2** on an **Ubuntu on Windows (WSL)** environment. It covers environment setup with Linux Homebrew, JDK 17, PostgreSQL 14, Apache Tomcat server configuration, and DHIS2 deployment.

## 🚀 Why DHIS2?

DHIS2 (District Health Information System 2) is an open-source platform widely used for health information management and monitoring. It is designed to capture, analyze, and visualize data, making it an essential tool for public health systems worldwide.

## 🛠️ System Requirements

- **Operating System:** Windows 10/11 with Windows Subsystem for Linux (WSL 2) running Ubuntu
- **Package Manager:** Homebrew (Linux version)
- **Java Development Kit (JDK):** OpenJDK Version 17
- **Database:** PostgreSQL (Version 14 or higher)
- **Web Server:** Apache Tomcat (Version 9 or higher)
- **Disk Space:** Minimum 10 GB free

## 📂 Project Structure

```text
dhis2-setup/
├── README.md
├── 1. environment_setup_for_ubuntu_wsl.md
├── 2. Postgersql (ubuntu_wsl).md
├── 3. apache_tomcat_(ubuntu_wsl).md
├── 4. dhis2_setup_(ubuntu_wsl).md
└── images/
    ├── java -version.png
    ├── psql --version.png
    ├── tomcat.png
    └── dhis2_login.png
```

## 📝 Installation Steps

1. **[Environment Setup](https://github.com/HaddyMiSol/dhis2-setup/blob/main/1.%20environment_setup_for_ubuntu_wsl.md):** Install Linux Homebrew, OpenJDK 17, configure your PATH/`JAVA_HOME`, and verify the Java installation.
2. **[PostgreSQL Installation](https://github.com/HaddyMiSol/dhis2-setup/blob/main/2.%20Postgresql%20(ubuntu_wsl).md):** Install PostgreSQL 14 via Linux Homebrew, configure users and databases, and set up management tools.
3. **[Tomcat Server Configuration](https://github.com/HaddyMiSol/dhis2-setup/blob/main/3.%20apache_tomcat_(ubuntu_wsl).md):** Install Apache Tomcat, configure environment variables in `~/.bashrc`, and manage server states.
4. **[DHIS2 Configuration](https://github.com/HaddyMiSol/dhis2-setup/blob/main/4.%20dhis2_setup_(ubuntu_wsl).md):** Download the DHIS2 WAR file, configure `dhis.conf`, and deploy it to the Tomcat webapps directory.

## 🌐 Accessing DHIS2

Once the server is up and running inside your WSL environment, open your Windows web browser and access DHIS2 at:

```text
http://localhost:8080/dhis
```

**Default Login Credentials:**
- **Username:** `admin`
- **Password:** `district`

## 🖼️ Screenshots

| Step | Screenshot |
| :--- | :--- |
| Environment Setup | ![Java Version](../images/java -version.png) |
| PostgreSQL Installation | ![PostgreSQL Version](../images/psql --version.png) |
| Tomcat Server Configuration | ![Tomcat Version](../images/tomcat.png) |
| DHIS2 Login Page | ![DHIS2 Login](../images/dhis2_login.png) |

## 🚑 Troubleshooting

Here are some common issues and solutions for WSL environments:

- **Java Version Not Recognized:** Check with `java -version` and ensure your `~/.bashrc` includes the correct `JAVA_HOME` export.
- **PostgreSQL Connection Error:** Restart the service using Linux brew services: `brew services restart postgresql@14`.
- **DHIS2 Not Starting / Access Issues:** Check Tomcat logs using `tail -f $CATALINA_HOME/logs/catalina.out` inside your WSL terminal.
- **Browser Accessibility:** Ensure you are accessing `localhost` from your Windows host browser while Tomcat runs in WSL.

## 💡 Contributing

If you encounter issues or have suggestions, feel free to open an issue or submit a pull request.

## 📄 License

This project is licensed under the MIT License. See the LICENSE file for details.

## ✨ Acknowledgements

- DHIS2 Documentation
- Homebrew on Linux (Homebrew on WSL)
- PostgreSQL Official Site
- Apache Tomcat