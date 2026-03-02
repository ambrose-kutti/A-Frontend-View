# 🚀 A-Frontend-View

<div align="center">

<!-- TODO: Add project logo -->

[![GitHub stars](https://img.shields.io/github/stars/ambrose-kutti/A-Frontend-View?style=for-the-badge)](https://github.com/ambrose-kutti/A-Frontend-View/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/ambrose-kutti/A-Frontend-View?style=for-the-badge)](https://github.com/ambrose-kutti/A-Frontend-View/network)
[![GitHub issues](https://img.shields.io/github/issues/ambrose-kutti/A-Frontend-View?style=for-the-badge)](https://github.com/ambrose-kutti/A-Frontend-View/issues)
[![GitHub license](https://img.shields.io/badge/license-No%20License%20Detected-lightgrey?style=for-the-badge)](LICENSE)

**A versatile web UI for real-time media streaming, local file uploads, and YouTube video playback.**

</div>

## 📖 Overview

A-Frontend-View is a straightforward web application designed to provide a unified interface for various media streaming and management tasks. It allows users to view RTSP streams live, upload local image and video files, and stream YouTube videos directly within the browser. The application leverages a Python FastAPI backend for robust media processing and content serving, coupled with a responsive HTML, CSS, and JavaScript frontend for an intuitive user experience. It's ideal for quick deployment in scenarios requiring basic media surveillance, content aggregation, or local media demonstration.

## ✨ Features

-   🎯 **RTSP Live Stream Integration**: Connect to and display real-time RTSP video feeds in the web UI.
-   ⬆️ **Local Media Uploads**: Easily upload images and videos from your local machine to the server.
-   ▶️ **YouTube Video Streaming**: Play YouTube videos by simply providing their URLs.
-   ⚙️ **FFmpeg Powered**: Utilizes FFmpeg for powerful backend media processing and stream handling.
-   📱 **Simple & Responsive UI**: A clean, easy-to-use web interface built with HTML, CSS, and JavaScript.
-   🔗 **Direct File Access**: Uploaded media can be accessed and streamed directly through the application.

## 🖥️ Screenshots

<!-- TODO: Add actual screenshots of RTSP stream, upload interface, and YouTube player. -->
The User Interface Page:
<img width="1190" height="620" alt="Screenshot 2026-02-25 124835" src="https://github.com/user-attachments/assets/4c6da23b-7505-4f24-8d73-6c03aa8bfd7f" />
The Local file Upload and Preview side:
<img width="1162" height="620" alt="Screenshot 2026-02-25 125520" src="https://github.com/user-attachments/assets/0896b55f-bd86-4e08-ae97-4dc73c84dcd2" />
The Youtube video Upload and Preview side:


## 🛠️ Tech Stack

**Frontend:**
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

**Backend:**
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Uvicorn](https://img.shields.io/badge/Uvicorn-FF4081?style=for-the-badge&logo=uvicorn&logoColor=white)
![Jinja2](https://img.shields.io/badge/Jinja2-000000?style=for-the-badge&logo=jinja&logoColor=white)

**Tools & Utilities:**
![FFmpeg](https://img.shields.io/badge/FFmpeg-007700?style=for-the-badge&logo=ffmpeg&logoColor=white)
![UUID](https://img.shields.io/badge/UUID-black?style=for-the-badge)

## 🚀 Quick Start

Follow these steps to get your development environment set up and running.

### Prerequisites

Before you begin, ensure you have the following installed on your system:

-   **Python** (version 3.9 or higher)
    -   [Download Python](https://www.python.org/downloads/)
-   **FFmpeg** (must be installed and available in your system's PATH)
    -   **Linux (Debian/Ubuntu):** `sudo apt update && sudo apt install ffmpeg`
    -   **macOS:** `brew install ffmpeg` (using Homebrew)
    -   **Windows:** Download binaries from [ffmpeg.org](https://ffmpeg.org/download.html) and add the `bin` directory to your system's PATH.

### Installation

1.  **Clone the repository**
    ```bash
    git clone https://github.com/ambrose-kutti/A-Frontend-View.git
    cd A-Frontend-View
    ```

2.  **Create and activate a virtual environment**
    ```bash
    python -m vvenv venv
    # On Linux/macOS
    source venv/bin/activate
    # On Windows
    .\venv\Scripts\activate
    ```

3.  **Install Python dependencies**
    ```bash
    pip install fastapi uvicorn python-multipart Jinja2
    ```
    *(Note: While `fastapi[all]` can install many extras, listing specific dependencies ensures clarity.)*

### Running the Application

1.  **Start the development server**
    ```bash
    uvicorn app:app --host 0.0.0.0 --port 8000 --reload
    ```
    The `--reload` flag enables auto-reloading on code changes, useful for development.

2.  **Open your browser**
    Visit `http://localhost:8000`

## 📁 Project Structure

```
A-Frontend-View/
├── .gitattributes
├── .gitignore
├── Contents Used and running file.txt # Important notes and setup instructions
├── README.md                      # This README file
├── app.py                         # Main FastAPI backend application
├── static/                        # Contains static assets (CSS, JavaScript, images)
│   ├── index.js                   # Frontend JavaScript logic
│   └── style.css                  # Frontend styling
│   └── # Other static assets like default images, favicons etc.
└── templates/                     # HTML templates served by FastAPI
    └── index.html                 # Main entry point HTML file for the UI
```

## ⚙️ Configuration

The application is largely configured via the `app.py` script itself.

### Environment Variables

Currently, no explicit `.env` file or environment variables are used for configuration. The application defaults to running on `http://0.0.0.0:8000`. You can change the port and host directly in the `uvicorn` command.

### Configuration Files

-   **`app.py`**: Contains the core logic and routing for the FastAPI application. Any server-side parameters or paths would be defined here.
-   **`Contents Used and running file.txt`**: This file contains crucial developer notes and setup instructions specific to the project's operation, including technologies used and running commands.

## 📚 API Reference

The FastAPI backend exposes several endpoints to manage media streams and uploads.

### Main UI

-   **`GET /`**
    -   Serves the main `index.html` file, which is the frontend of the application.

### Media Uploads

-   **`POST /upload_image`**
    -   **Description**: Accepts an image file for upload.
    -   **Request Body**: `multipart/form-data` containing the image file.

-   **`POST /upload_video`**
    -   **Description**: Accepts a video file for upload.
    -   **Request Body**: `multipart/form-data` containing the video file.

### Streaming

-   **`GET /rtsp_stream/{stream_url}`**
    -   **Description**: Initiates and serves an RTSP stream (e.g., converted via FFmpeg) to the frontend.
    -   **Parameters**:
        -   `stream_url` (path parameter): The URL of the RTSP stream.

-   **`GET /youtube_stream/{video_id}`**
    -   **Description**: Fetches and streams a YouTube video to the frontend.
    -   **Parameters**:
        -   `video_id` (path parameter): The ID of the YouTube video.

*(Note: Specific implementation details, such as how streams are delivered (e.g., SSE, WebSockets, or direct HLS/DASH conversion) would be found within `app.py` and `static/index.js`.)*

## 🤝 Contributing

We welcome contributions to A-Frontend-View! If you have suggestions for improvements or new features, please feel free to fork the repository and submit a pull request.

### Development Setup for Contributors

1.  Follow the **Quick Start** instructions above to set up your environment.
2.  Make your desired changes in the `app.py`, `templates/index.html`, or `static/` directories.
3.  Ensure your changes align with the project's goal of providing a simple media viewer.

## 📄 License

This project does not explicitly specify a license. Please refer to the repository owner for licensing information.

## 🙏 Acknowledgments

-   **FastAPI**: For providing a modern, fast (high-performance) web framework for building APIs with Python.
-   **Uvicorn**: The ASGI server used to run FastAPI applications.
-   **FFmpeg**: The powerful multimedia framework essential for handling diverse media streams and conversions.
-   **Jinja2**: For flexible templating in the backend.

## 📞 Support & Contact

-   🐛 Issues: Feel free to report issues on the [GitHub Issues page](https://github.com/ambrose-kutti/A-Frontend-View/issues).
-   👤 Author: [Ambrose Kutti](https://github.com/ambrose-kutti)

---

<div align="center">

**⭐ Star this repo if you find it helpful!**

Made with ❤️ by [ambrose-kutti](https://github.com/ambrose-kutti)

</div>
