# Hacktiv8 Chatbot

A modern AI-powered chatbot application built with **Google Gemini API** and **ExpressJS**, providing intelligent conversational capabilities with a clean and intuitive interface.

## Overview

This chatbot application leverages the power of Google's Gemini AI model to deliver natural language understanding and generation. Built on ExpressJS, it provides a robust backend API with a user-friendly interface for interactive conversations.

## Features

- 🤖 **AI-Powered Conversations** - Powered by Google Gemini API for intelligent responses
- 🚀 **Express Backend** - Fast and scalable Node.js/ExpressJS server
- 💬 **Real-time Chat** - Interactive messaging interface
- 🔒 **Secure API Keys** - Environment-based configuration for sensitive data
- 📱 **Responsive Design** - Works seamlessly on desktop and mobile devices
- 🎯 **Context-Aware** - Maintains conversation context for coherent dialogue
- ⚡ **Fast Response Times** - Optimized for quick API responses

## Tech Stack

- **Backend**: ExpressJS (Node.js)
- **AI Engine**: Google Gemini API
- **Runtime**: Node.js
- **Frontend**: (HTML/CSS/JavaScript or specify your framework)
- **Environment Management**: dotenv

## Prerequisites

Before running this application, ensure you have:

- **Node.js** (v14 or higher)
- **npm** (v6 or higher)
- **Google Cloud Account** with Gemini API enabled
- **API Key** from Google Cloud Console

## Installation

### 1. Clone the Repository

```bash
git clone <repository-url>
cd Hacktiv8_chat_bot
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Set Up Environment Variables

Create a `.env` file in the root directory:

```env
GOOGLE_API_KEY=your_google_gemini_api_key_here
PORT=3000
NODE_ENV=development
```

### 4. Get Your Google Gemini API Key

1. Go to [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Click "Create API Key"
3. Copy your API key
4. Paste it in your `.env` file as `GOOGLE_API_KEY`

## Usage

### Start the Server

```bash
npm start
```

The server will start on `http://localhost:3000` (or your configured PORT).

### Development Mode

For development with auto-reload:

```bash
npm run dev
```

## Project Structure

```
Hacktiv8_chat_bot/
├── src/
│   ├── server.js          # Main Express application
│   ├── routes/            # API routes
│   ├── controllers/       # Request handlers
│   ├── services/          # Gemini API integration
│   └── config/            # Configuration files
├── public/                # Static files (HTML, CSS, JS)
├── .env                   # Environment variables (create this)
├── .gitignore            # Git ignore file
├── package.json          # Dependencies and scripts
├── README.md             # This file
└── credential.md         # Credentials documentation
```

## API Endpoints

### Send a Message

**POST** `/api/chat`

Request body:
```json
{
  "message": "Your message here",
  "conversationId": "optional-conversation-id"
}
```

Response:
```json
{
  "success": true,
  "message": "Chatbot response",
  "conversationId": "conversation-id",
  "timestamp": "2026-05-09T10:30:00Z"
}
```

### Get Conversation History

**GET** `/api/chat/:conversationId`

Response:
```json
{
  "success": true,
  "conversationId": "conversation-id",
  "messages": [
    {
      "role": "user",
      "content": "User message",
      "timestamp": "2026-05-09T10:30:00Z"
    },
    {
      "role": "assistant",
      "content": "Chatbot response",
      "timestamp": "2026-05-09T10:30:05Z"
    }
  ]
}
```

### Clear Conversation

**DELETE** `/api/chat/:conversationId`

Response:
```json
{
  "success": true,
  "message": "Conversation cleared"
}
```

## Configuration

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `GOOGLE_API_KEY` | Google Gemini API key | Yes |
| `PORT` | Server port number | No (default: 3000) |
| `NODE_ENV` | Environment (development/production) | No (default: development) |

## Development

### Available Scripts

```bash
# Start the server
npm start

# Start with nodemon (auto-reload)
npm run dev

# Run tests
npm test

# Lint code
npm run lint
```

### Folder Structure Explanation

- **src/routes/** - Defines all API endpoints
- **src/controllers/** - Handles request/response logic
- **src/services/** - Manages Gemini API calls
- **public/** - Frontend files (HTML, CSS, JavaScript)

## Error Handling

The application includes comprehensive error handling:

- Invalid API requests
- Missing environment variables
- Gemini API errors
- Network timeouts
- Malformed JSON requests

All errors return appropriate HTTP status codes and descriptive messages.

## Security Considerations

- ✅ **API Key Protection**: Never commit `.env` file to version control
- ✅ **Input Validation**: All user inputs are validated
- ✅ **Rate Limiting**: Consider implementing rate limiting in production
- ✅ **HTTPS**: Use HTTPS in production environments
- ✅ **CORS**: Configure CORS appropriately for your frontend

## Troubleshooting

### Issue: "API Key not found"
**Solution**: Ensure your `.env` file contains the `GOOGLE_API_KEY` variable

### Issue: "Cannot connect to Gemini API"
**Solution**: Check your internet connection and verify the API key is valid

### Issue: Port already in use
**Solution**: Change the PORT in `.env` or kill the process using that port

### Issue: Module not found errors
**Solution**: Run `npm install` to ensure all dependencies are installed

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For issues, questions, or suggestions, please:

- Open an issue on GitHub
- Check existing documentation
- Refer to [Google Gemini API Documentation](https://ai.google.dev/docs)
- Check [ExpressJS Documentation](https://expressjs.com/)

## Acknowledgments

- Google Gemini API for AI capabilities
- ExpressJS community
- Hacktiv8 for the opportunity

## Changelog

### v1.0.0 (2026-05-09)
- Initial release
- Basic chat functionality
- Gemini API integration
- Express server setup

---

**Happy Coding! 🚀**
