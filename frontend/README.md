# OpenAI Chat Frontend

A beautiful, modern chat interface built with Next.js and TypeScript for interacting with the OpenAI Chat API backend.

## Features

- 🎨 **Modern UI**: Beautiful, responsive design with dark/light theme support
- 🔐 **Secure**: API key input with password-style field and client-side validation
- ⚡ **Real-time Streaming**: Live streaming responses from OpenAI's GPT models
- 📱 **Responsive**: Works perfectly on desktop, tablet, and mobile devices
- ⚙️ **Configurable**: Adjustable system messages and model selection
- 🎯 **User-friendly**: Intuitive chat interface with typing indicators and message history

## Prerequisites

- Node.js 18.0 or higher
- npm or yarn package manager
- The FastAPI backend server running (see `../api/README.md`)
- An OpenAI API key

## Installation

1. **Navigate to the frontend directory:**
   ```bash
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Set up environment variables:**
   ```bash
   cp .env.example .env.local
   ```
   
   Edit `.env.local` and update the API URL if needed:
   ```
   NEXT_PUBLIC_API_URL=http://localhost:8000
   ```

## Running the Application

### Development Mode

Start the development server:
```bash
npm run dev
```

The application will be available at `http://localhost:3000`

### Production Build

1. **Build the application:**
   ```bash
   npm run build
   ```

2. **Start the production server:**
   ```bash
   npm start
   ```

## Usage

1. **Start the Backend**: Make sure the FastAPI backend is running on `http://localhost:8000`

2. **Open the Frontend**: Navigate to `http://localhost:3000` in your browser

3. **Enter API Key**: On first visit, you'll be prompted to enter your OpenAI API key
   - Get your API key from [OpenAI Platform](https://platform.openai.com/api-keys)
   - The key is stored securely in your browser session only

4. **Start Chatting**: 
   - Type your message in the input field
   - Press Enter to send (Shift+Enter for new lines)
   - Watch as the AI responds in real-time with streaming

5. **Configure Settings** (Optional):
   - Click the settings icon to adjust the system message
   - Select different GPT models (gpt-4.1-mini, gpt-4, gpt-3.5-turbo)
   - Customize how the AI should behave

## Deployment

### Vercel Deployment

This frontend is optimized for deployment on Vercel:

1. **Connect your repository** to Vercel
2. **Set environment variables** in the Vercel dashboard:
   - `NEXT_PUBLIC_API_URL`: Your deployed backend API URL
3. **Deploy**: Vercel will automatically build and deploy your application

### Manual Deployment

1. **Build the application:**
   ```bash
   npm run build
   ```

2. **Export static files** (optional):
   ```bash
   npm run export
   ```

3. **Deploy the `out/` or `.next/` directory** to your hosting provider

## Project Structure

```
frontend/
├── components/           # React components
│   ├── ApiKeySetup.tsx  # API key input component
│   ├── ChatInterface.tsx # Main chat interface
│   └── MessageBubble.tsx # Individual message component
├── pages/               # Next.js pages
│   ├── _app.tsx        # App wrapper
│   ├── _document.tsx   # HTML document structure
│   └── index.tsx       # Main page
├── styles/             # Global styles
│   └── globals.css     # Tailwind CSS and custom styles
├── types/              # TypeScript type definitions
│   └── index.ts        # Shared types
└── public/             # Static assets
```

## Configuration

### Environment Variables

- `NEXT_PUBLIC_API_URL`: The URL of your FastAPI backend (default: http://localhost:8000)

### Styling

The application uses Tailwind CSS with a custom design system:
- Proper contrast ratios for accessibility
- Responsive breakpoints for mobile-first design
- Dark/light theme variables
- Custom animations and transitions

## Troubleshooting

### Common Issues

1. **"Backend server is not accessible"**
   - Ensure the FastAPI backend is running on the correct port
   - Check that CORS is properly configured in the backend
   - Verify the `NEXT_PUBLIC_API_URL` environment variable

2. **API Key Issues**
   - Ensure your OpenAI API key starts with "sk-"
   - Check that you have sufficient credits in your OpenAI account
   - Verify the key has the necessary permissions

3. **Build Errors**
   - Run `npm install` to ensure all dependencies are installed
   - Check for TypeScript errors with `npm run lint`
   - Ensure Node.js version is 18.0 or higher

4. **Streaming Not Working**
   - Check browser console for JavaScript errors
   - Verify the backend is returning streaming responses
   - Test the backend API directly to isolate issues

### Performance Tips

- The application automatically handles message history and scrolling
- Streaming responses provide immediate feedback without waiting for complete responses
- API keys are stored securely in browser session storage
- Messages are optimized for mobile viewing with responsive design

## Security Notes

- API keys are stored only in browser session storage and never sent to our servers
- All communication with OpenAI happens through your own API key
- HTTPS is recommended for production deployments
- Consider implementing rate limiting for production use

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## Support

For issues and questions:
1. Check the troubleshooting section above
2. Verify the backend API is working correctly
3. Check browser console for error messages
4. Ensure environment variables are set correctly