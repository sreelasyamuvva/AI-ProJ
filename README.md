# AI-Driven English Communication Platform

An AI-powered web platform designed to help users improve their English communication skills through interactive conversations, group discussions, and presentation summarization.

> **Note:** This is an academic project developed as part of the Software Engineering Lab at Rajiv Gandhi University of Knowledge Technologies (RGUKT), Ongole. For detailed information about the project's design, implementation, UML diagrams, testing, screenshots, and technical documentation, please refer to [`documentation.pdf`](documentation.pdf).   
**If the PDF does not open in GitHub's preview, download the raw file and open it locally.**

## Overview

The **AI-Driven English Communication Platform** provides an interactive environment for practicing English communication and improving fluency, confidence, listening, and comprehension skills.

The platform combines conversational AI, speech processing, and presentation summarization into a single application.

It provides three primary features:

- **Group Discussion** – Simulated discussions with multiple participants to practice conversational fluency and group communication.
- **One-on-One AI Conversation** – Voice-based interaction with an AI assistant using speech-to-text, AI-generated responses, and text-to-speech.
- **Slide Summarizer** – Upload a PowerPoint presentation and generate concise summaries of individual slides to improve comprehension and review efficiency.

The project was developed as part of the **Software Engineering Lab** at Rajiv Gandhi University of Knowledge Technologies, Ongole.

---

## Key Features

### 1. Group Discussion

The Group Discussion module provides a structured discussion environment where users can participate in conversations around a selected topic.

The system:

- Generates a discussion topic.
- Simulates multiple participants.
- Allows the user to contribute to the discussion.
- Generates AI responses from the other participants.
- Provides vocabulary and grammar suggestions for user inputs.
- Maintains the flow of the discussion.

The module is designed to help users improve:

- Conversational fluency
- Vocabulary
- Grammar
- Confidence in group communication

---

### 2. One-on-One AI Conversation

The One-on-One Conversation module enables users to interact with an AI English communication assistant through voice.

The interaction flow includes:

1. User provides voice input.
2. Speech is converted into text.
3. The text is processed by the conversational AI.
4. An AI-generated response is produced.
5. The response can be converted back into speech.

This provides an interactive environment for practicing:

- Speaking
- Listening
- Conversational English
- Real-time communication

---

### 3. Slide Summarizer

The Slide Summarizer allows users to upload a `.pptx` presentation.

The system:

1. Accepts the PowerPoint file.
2. Extracts text and images from the slides.
3. Processes the extracted content.
4. Uses an AI model to generate content based on the slide.
5. Produces a concise, presentation-oriented summary for each slide.

This feature is useful for quickly understanding academic or business presentations.

---

## System Modules

The project is organized around three major user-facing capabilities along with supporting application modules.

### Home Page Module

Provides the main interface and navigation to:

- Group Discussions
- One-on-One Conversations
- Slide Summarization

### User Module

Handles user interactions with the platform, including:

- Starting discussions
- Conversing with the AI
- Uploading presentations
- Accessing generated results
- Conversation history and feedback

### Admin Module

Provides administrative functionality for:

- User management
- Session management
- Activity monitoring
- Data analytics
- Error handling
- System management

The platform also includes supporting pages such as an About page, Technical Details page, and Contact Form.

---

## Technology Stack

### Frontend

- HTML
- CSS
- JavaScript

### Backend

- Python
- Flask

### AI & Language Processing

- Google Generative AI
- Groq
- Deepgram SDK

### Presentation Processing

- `python-pptx`
- Pillow

### Other Technologies

- Flask-CORS
- REST-style API endpoints
- Session management
- File upload and processing

The project uses `python-pptx` for extracting information from PowerPoint files, Pillow for image processing, Google Generative AI for language generation, Groq for efficient AI processing, and Deepgram for speech processing. :contentReference[oaicite:1]{index=1}

---

## Architecture

The platform follows a web-based frontend/backend architecture.

```text
                         ┌──────────────────────┐
                         │        User          │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │    Web Interface     │
                         │   HTML/CSS/JS        │
                         └──────────┬───────────┘
                                    │
                                    ▼
                         ┌──────────────────────┐
                         │    Flask Backend     │
                         │       Python         │
                         └──────────┬───────────┘
                                    │
              ┌─────────────────────┼─────────────────────┐
              │                     │                     │
              ▼                     ▼                     ▼
      ┌───────────────┐     ┌───────────────┐     ┌───────────────┐
      │ Group         │     │ One-on-One    │     │ Slide         │
      │ Discussion    │     │ Conversation  │     │ Summarizer    │
      └───────┬───────┘     └───────┬───────┘     └───────┬───────┘
              │                     │                     │
              ▼                     ▼                     ▼
       Google GenAI /       Deepgram + AI          python-pptx
       Groq                  + Text-to-Speech       + Pillow
