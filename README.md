<div align="center">
  <img src="https://www.theapollouniversity.edu.in/assets/images/logo.png" alt="The Apollo University Logo" width="200"/>
  <h1>Offline AI Chatbot System using Open-Source LLMs and Local Network Topology</h1>
  <p>
    A Mini Project Report Submitted in partial fulfillment of the requirements for the award of the degree of Bachelor of Technology in Computer Science and Engineering (Artificial Intelligence & Data Science)
  </p>
  <p>
    <strong>Submitted by:</strong> Pavan Adabala (122210701103) <br/>
    <strong>Under the Guidance of:</strong> Dr. A. B. Manju
  </p>
  <p>
    <strong>Academic Year: 2024–2025</strong>
  </p>
  <p>
    DEPARTMENT OF COMPUTER SCIENCE AND ENGINEERING (AI&DS) <br/>
    <strong>THE APOLLO UNIVERSITY</strong> <br/>
    CHITTOOR – ANDHRA PRADESH, INDIA
  </p>
</div>

<div align="center">

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/your-repo/your-project?style=social)](https://github.com/your-repo/your-project/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/your-repo/your-project?style=social)](https://github.com/your-repo/your-project/network/members)

</div>

---

## 📖 Abstract

The proliferation of AI-powered conversational agents has transformed user interaction with technology. However, the majority of these systems rely on cloud-based APIs, raising significant concerns about data privacy, latency, and operational costs, especially within sensitive environments like university campuses. This project addresses these challenges by designing and implementing a fully **Offline AI Chatbot System** tailored for a university campus.

The system leverages open-source Large Language Models (LLMs) such as **Mistral 7B, Qwen 2.5, and a specialized Med-LLaMA**, which are hosted locally on a dedicated server using **LM Studio**. This architecture ensures that all data processing occurs within the campus network, guaranteeing complete data privacy and eliminating dependency on internet connectivity. The chatbot is accessible to students and faculty via a browser-based interface powered by **OpenWebUI**, connected to the campus Wireless Local Area Network (WLAN).

The chatbot's functionalities are twofold: it provides academic support by answering queries related to subjects, lab procedures, and campus information, and it offers health and wellness guidance through the Med-LLaMA model. This integrated health module provides symptom-based advice and dietary suggestions, promoting student well-being. For secure, temporary remote access, the system incorporates **Ngrok** tunneling, creating an HTTPS endpoint for authenticated users outside the primary network.

The project's core contribution is the creation of a **self-sustained, private, and intelligent AI ecosystem**. By deploying edge-based AI, this work demonstrates a scalable, secure, and cost-effective model for digital self-reliance in educational institutions, enhancing real-time interaction and information accessibility without compromising security.

## ✨ Key Features

-   🔒 **100% Offline & Private**: All data and queries are processed on a local server within the campus network. No data ever leaves the premises.
-   🚀 **Low Latency**: Delivers near-instantaneous responses by eliminating internet round-trip time.
-   🧠 **Powered by Open-Source LLMs**: Utilizes powerful models like Mistral 7B for academic queries and Med-LLaMA for specialized health advice.
-   🌐 **User-Friendly Web Interface**: A clean, modern chat interface provided by OpenWebUI, accessible from any device with a web browser.
-   🤝 **Multi-Domain Support**: Seamlessly switch between a general academic assistant and a specialized health & wellness advisor.
-   🔗 **Secure Remote Access**: Optional, secure remote access for authorized users via Ngrok's encrypted HTTPS tunnels.
-   💰 **Cost-Effective**: A one-time hardware investment eliminates recurring API subscription costs associated with cloud-based solutions.
-   🔧 **Easy Management**: Simplified model management and server setup using the intuitive LM Studio application.

## 🛠️ Tech Stack & Tools

| Component           | Technology / Tool                                                                                                                                                             |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **LLM Hosting**     | <img src="https://avatars.githubusercontent.com/u/140223592?s=48&v=4" alt="LM Studio Logo" width="20"/> **LM Studio**                                                              |
| **Frontend UI**     | <img src="https://avatars.githubusercontent.com/u/150538356?s=48&v=4" alt="OpenWebUI Logo" width="20"/> **OpenWebUI**                                                              |
| **Containerization**| <img src="https://www.docker.com/wp-content/uploads/2022/03/Moby-logo.png" alt="Docker Logo" width="20"/> **Docker**                                                               |
| **LLM Models**      | <img src="https://mistral.ai/images/logo.svg" alt="Mistral Logo" width="20"/> **Mistral 7B**, Qwen 2.5, Med-LLaMA (GGUF)                                                          |
| **Remote Tunneling**| <img src="https://static.ngrok.com/images/logos/ngrok-logo-trans-bck.png" alt="Ngrok Logo" width="20"/> **Ngrok**                                                                  |
| **Server OS**       | <img src="https://assets.ubuntu.com/v1/29985a98-ubuntu-logo32.png" alt="Ubuntu Logo" width="20"/> **Ubuntu Linux** (Recommended)                                                   |

## 🏗️ System Architecture

The system uses a multi-tiered architecture for modularity and separation of concerns.

<div align="center">
  <img src="https://i.imgur.com/n14zG3k.png" alt="System Architecture Diagram" width="700"/>
</div>

-   **Presentation Layer (Client-side)**: The OpenWebUI front-end, which runs in the user's browser and provides the chat interface.
-   **Application Layer (Server-side)**: The OpenWebUI backend, which receives requests from the client and forwards them to the Model Layer.
-   **Model Layer (AI Engine)**: LM Studio, which loads the LLMs and exposes a local, OpenAI-compatible REST API for the Application Layer to consume.

### 🌐 Network Topology

The server is connected to the university's core network, making it accessible to any user on the campus WLAN via a local IP address. All traffic is contained within the local network, ensuring speed and security.

<div align="center">
  <img src="https://i.imgur.com/R0UjNqw.png" alt="Network Topology Diagram" width="600"/>
</div>

## 🚀 Getting Started: Setup & Installation

Follow these steps to set up the offline chatbot system on your own server.

### Hardware Prerequisites

| Component    | Minimum Specification                                    | Purpose                                   |
| ------------ | -------------------------------------------------------- | ----------------------------------------- |
| **GPU**      | NVIDIA GeForce RTX 30/40 Series with >= 12 GB VRAM       | Crucial for accelerating LLM inference.   |
| **RAM**      | 32 GB DDR4 or higher                                     | To load large language models into memory.|
| **CPU**      | Modern Multi-core CPU (Intel i7/i9 or AMD Ryzen 7/9)     | General processing tasks.                 |
| **Storage**  | 1 TB NVMe SSD or higher                                  | To store multiple large LLM files.        |

### Step 1: Install LM Studio & Download Models

First, install the application that will serve the language models.

*   **Windows / macOS**:
    1.  Go to the official **[LM Studio download page](https://lmstudio.ai/)**.
    2.  Download the correct installer for your operating system (`.exe` for Windows, `.dmg` for macOS).
    3.  Run the installer and follow the on-screen instructions.
*   **Linux**:
    1.  Go to the official **[LM Studio download page](https://lmstudio.ai/)** and download the `.AppImage` file.
    2.  Open a terminal, navigate to your downloads folder, and make the file executable:
        ```bash
        chmod +x LM_Studio-*.AppImage
        ```
    3.  Run LM Studio:
        ```bash
        ./LM_Studio-*.AppImage
        ```

Once LM Studio is running:
1.  Use the search tab (🔍 icon) to find and download your desired models. Look for **GGUF** formats from reputable creators like "The Bloke". Good starting models include:
    -   `Mistral 7B Instruct v0.2`
    -   `Med-LLaMA`
2.  Go to the local server tab (↔️ icon).
3.  Select a downloaded model from the dropdown list.
4.  In the right-hand panel, set **GPU Offload** to `Max` to ensure the best performance.
5.  Click **Start Server**. Your local, OpenAI-compatible API is now running at `http://localhost:12221/v1` (or your configured port).

### Step 2: Install Docker & Docker Compose

Docker is used to easily run the OpenWebUI front-end in an isolated container.

*   **Windows / macOS**:
    1.  Download and install **[Docker Desktop](https://www.docker.com/products/docker-desktop/)**. It includes Docker Compose automatically.
    2.  Start Docker Desktop and ensure the whale icon is stable in your system tray or menu bar.
*   **Linux**:
    1.  Follow the official guide to **[install Docker Engine for your Linux distribution](https://docs.docker.com/engine/install/)**.
    2.  Ensure the Docker service is running:
        ```bash
        sudo systemctl start docker
        sudo systemctl enable docker
        ```
    3.  (Optional but recommended) Add your user to the `docker` group to run commands without `sudo`. You will need to log out and back in for this to take effect.
        ```bash
        sudo usermod -aG docker $USER
        ```

### Step 3: Set Up & Run OpenWebUI

1.  Open your command line tool (Terminal on macOS/Linux, PowerShell on Windows).
2.  Create a new directory for the project and navigate into it:
    ```bash
    mkdir offline-chatbot
    cd offline-chatbot
    ```
3.  Create a file named `docker-compose.yml`. Copy and paste the following content into it.
    
    > **IMPORTANT**: Find your server's local IP address and replace `YOUR_SERVER_IP` in the file below.
    > -   **Windows**: Run `ipconfig` in Command Prompt and look for "IPv4 Address".
    > -   **macOS**: Run `ifconfig | grep "inet "` in Terminal.
    > -   **Linux**: Run `hostname -I` in Terminal.

    ```yaml
    version: '3.8'
    services:
      open-webui:
        image: ghcr.io/open-webui/open-webui:main
        container_name: open-webui
        ports:
          - "3000:8080"
        environment:
          # 👇 Replace YOUR_SERVER_IP with the actual local IP of the machine running LM Studio
          - 'OPENAI_API_BASE_URL=http://YOUR_SERVER_IP:12221/v1' 
          - 'OPENAI_API_KEY=not-needed'
        volumes:
          - ./open-webui:/app/backend/data
        restart: unless-stopped
    ```

4.  From the `offline-chatbot` directory, run the container:
    ```bash
    docker-compose up -d
    ```
5.  The web interface is now running! Access it by navigating to `http://<YOUR_SERVER_IP>:3000` in a browser. The first user to register will become the administrator.

### Step 4: (Optional) Secure Remote Access with Ngrok

1.  [Download and set up Ngrok](https://ngrok.com/docs/getting-started/) on your server.
2.  Authenticate your Ngrok agent (you only need to do this once).
    ```bash
    ngrok config add-authtoken <YOUR_NGROK_TOKEN>
    ```
3.  Start a secure tunnel to your OpenWebUI instance, adding a username and password for security.
    ```bash
    ngrok http 3000 --basic-auth "admin:YourSecurePassword123"
    ```
4.  Ngrok will provide a public HTTPS URL (`https://....ngrok-free.app`) that you can share with authorized remote users.

## 📸 Screenshots

<div align="center">
  <img src="https://raw.githubusercontent.com/open-webui/open-webui/main/docs/assets/images/screenshot-1.png" alt="OpenWebUI Chat Interface" width="700"/>
  <p><em>The clean and intuitive OpenWebUI chat interface.</em></p>
</div>

<div align="center">
  <img src="https://i.imgur.com/G5iE1A9.png" alt="Example academic query response" width="700"/>
  <p><em>Example of the chatbot responding to an academic query about Python.</em></p>
</div>


## 📊 Performance: Offline vs. Online

One of the key advantages is the significant reduction in latency. A comparison test shows the offline system is more than twice as fast as a comparable cloud-based service.

| System                                        | Average Response Time | Tokens per Second |
| --------------------------------------------- | --------------------- | ----------------- |
| **Offline System (Local Mistral 7B)**         | **~2.5 seconds**      | **~45 tokens/sec**|
| Online Service (Cloud-based API)              | ~6.8 seconds          | ~18 tokens/sec    |

This provides a much more fluid and interactive user experience, free from network lag.

## 💡 Future Enhancements

-   **IoT Integration**: Control smart campus devices (lights, AC) via the chatbot.
-   **Voice Commands**: Add Speech-to-Text and Text-to-Speech for a hands-free experience.
-   **Multi-Language Support**: Utilize multilingual LLMs to cater to a diverse student body.
-   **Enhanced Medical Capabilities**: Implement a RAG system to allow the Med-LLaMA model to consult a local medical knowledge base for more accurate advice.

## 🙏 Acknowledgement

I would like to express my deepest gratitude to my project guide, **Dr. A B Manju**, for his invaluable guidance, constant encouragement, and insightful feedback throughout the duration of this project. His expertise and vision were instrumental in shaping this work and bringing it to fruition.

I am also immensely thankful to the Head of the Department and all the faculty members of the Department of Computer Science and Engineering (AI & DS) at The Apollo University for providing the necessary infrastructure and a conducive environment.

My heartfelt appreciation goes to my friends, classmates, and family for their unwavering support and encouragement.

---

<div align="center">
  <em>This project demonstrates a powerful, private, and practical application of edge AI for educational institutions.</em>
</div>
