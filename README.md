# 🤖 GenAI.API

GenAI.API is an **ASP.NET Core 8 Web API** that leverages **Generative AI** to process uploaded files and generate structured content. The API supports uploading text, audio, and video files, automatically extracts and transcribes content using **Whisper**, and formats the output using **OpenAI**.

The project demonstrates how to build an AI-powered backend that integrates file processing, speech-to-text conversion, and Large Language Models (LLMs) into a single RESTful API.

---

# 🚀 Features

- 📁 Upload text, audio, and video files
- 🎙️ Speech-to-text transcription using Whisper
- 🎬 Audio extraction from video files using FFmpeg
- 🤖 AI-powered content generation using OpenAI
- 📄 Supports multiple file formats
- ⚡ RESTful API with Swagger documentation
- 🔄 Dependency Injection and Service Layer architecture
- 🌐 Configurable CORS policies
- 📦 Large file upload support (up to 100 MB)

---

# 🛠 Tech Stack

## Backend

- ASP.NET Core 8 Web API
- C#
- OpenAI API
- Whisper AI
- Xabe.FFmpeg
- Swagger / OpenAPI
- Dependency Injection
- REST API

---

# 📁 Project Structure

```text
GenAI.API
│
├── Controllers
│   ├── UploadController.cs
│   └── WeatherForecastController.cs
│
├── Models
│   ├── OpenAiResponse.cs
│   └── UploadRequest.cs
│
├── Services
│   ├── IOpenAiService.cs
│   ├── OpenAiService.cs
│   ├── IVideoService.cs
│   ├── VideoService.cs
│   ├── IWhisperService.cs
│   └── WhisperService.cs
│
├── Properties
│
├── Program.cs
├── appsettings.json
└── Dockerfile
```

---

# 🏗 System Architecture

```text
                 Client Application
                        │
                        ▼
             ASP.NET Core Web API
                        │
             UploadController
                        │
       ┌────────────────┼─────────────────┐
       ▼                ▼                 ▼
 Text Processing   Whisper Service   Video Service
       │                │                 │
       │                ▼                 ▼
       │          Speech-to-Text     FFmpeg Extraction
       │                │                 │
       └────────────────┴─────────────────┘
                        │
                        ▼
                OpenAI Service
                        │
                        ▼
             AI Generated Response
                        │
                        ▼
                  JSON Response
```

---

# 📂 Supported File Types

| File Type | Processing |
|-----------|------------|
| `.txt` | Reads text directly |
| `.mp3` | Whisper transcription |
| `.wav` | Whisper transcription |
| `.mp4` | Extracts audio using FFmpeg and transcribes using Whisper |

---

# 🔄 Processing Workflow

```text
Upload File
     │
     ▼
Validate File Type
     │
     ▼
Extract Content
     │
     ├─────────────► Text File
     │                    │
     │                    ▼
     │              Read Content
     │
     ├─────────────► Audio File
     │                    │
     │                    ▼
     │         Whisper Transcription
     │
     └─────────────► Video File
                          │
                          ▼
                 Extract Audio (FFmpeg)
                          │
                          ▼
                 Whisper Transcription
                          │
                          ▼
                 OpenAI Content Generation
                          │
                          ▼
                    JSON Response
```

---

# 📚 API Endpoints

## Upload File

**POST**

```
/Upload
```

### Request

**Form Data**

| Parameter | Type | Required |
|-----------|------|----------|
| file | IFormFile | Yes |
| outputType | string | Yes |

Supported output types can be customized depending on the OpenAI prompt implementation.

---

### Example Response

```json
{
  "content": "AI generated formatted content..."
}
```

---

# ⚙ Configuration

Configure your application settings inside:

```
appsettings.json
```

Update the required API keys and settings for:

- OpenAI API
- Whisper Service
- FFmpeg installation path (if required)

---

# ▶ Running the Project

## Clone Repository

```bash
git clone https://github.com/yourusername/GenAI.API.git
```

---

## Restore Packages

```bash
dotnet restore
```

---

## Build the Project

```bash
dotnet build
```

---

## Run the API

```bash
dotnet run
```

---

## Launch Swagger

```
https://localhost:5001/swagger
```

---

# 🌐 CORS Configuration

The API includes predefined CORS policies:

- Allow localhost Angular applications
- Allow all origins (configurable)

---

# 📈 Key Components

### Upload Controller

Responsible for:

- Receiving uploaded files
- Detecting supported file types
- Invoking transcription services
- Returning AI-generated content

---

### Whisper Service

Responsible for:

- Speech-to-text transcription
- Audio processing

---

### Video Service

Responsible for:

- Audio extraction from video
- Passing extracted audio for transcription

---

### OpenAI Service

Responsible for:

- Formatting extracted content
- Generating AI-enhanced responses

---

# 💡 Learning Outcomes

This project demonstrates:

- ASP.NET Core Web API Development
- OpenAI API Integration
- Whisper Speech Recognition
- Video Processing with FFmpeg
- Dependency Injection
- Service-Oriented Architecture
- File Upload Handling
- REST API Design
- Swagger Documentation
- AI-Powered Content Generation

---

# 🚀 Future Enhancements

- Authentication with JWT
- Vector Database Integration
- Retrieval-Augmented Generation (RAG)
- PDF and DOCX document support
- Azure OpenAI Integration
- Docker Compose
- Kubernetes Deployment
- Azure Blob Storage
- Real-time progress tracking
- Chat-based AI interface

---

# 👨‍💻 Author

**Praveen Anthati**

Senior .NET Developer

---

