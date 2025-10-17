# Watson Orchestrator Chat Interface

A beautiful, responsive web interface for IBM Watson Orchestrator with multiple deployment options and host validation bypass attempts.

## 🚀 Features

- **Modern UI**: Clean, professional design with gradient backgrounds
- **Responsive Layout**: Works on desktop and mobile devices
- **Multiple Versions**: Different configurations for various deployment scenarios
- **Host Validation Bypass**: Attempts to work around localhost restrictions
- **Debug Support**: Comprehensive logging and error handling

## 📁 Files

- `index.html` - Main chat interface with enhanced configuration
- `watson-bypass.html` - Aggressive host validation bypass version
- `test-watson.html` - Minimal test version with debug logging

## 🔧 Configuration

The Watson Orchestrator is configured with:

```javascript
window.wxOConfiguration = {
    orchestrationID: "20251002-0017-5466-8027-ffbdc3cb4c0e_20251002-0020-1670-60f1-755f8bce5ba9",
    hostURL: "https://dl.watson-orchestrate.ibm.com",
    rootElementID: "root",
    chatOptions: {
        agentId: "eb15a996-eec3-4d5f-8753-70cd7bd9c574", 
        agentEnvironmentId: "ffc889cf-eb4f-4967-aa47-2d9aefda8bf1"
    }
};
```

## 🚀 Deployment Options

### Vercel (Recommended)
1. Go to [vercel.com](https://vercel.com)
2. Sign up/Login
3. Click "New Project"
4. Drag and drop `index.html`
5. Deploy!

### Netlify
1. Go to [netlify.com](https://netlify.com)
2. Drag and drop `index.html`
3. Get your live URL

### GitHub Pages
1. Push to GitHub
2. Go to Settings → Pages
3. Select source branch
4. Deploy

## 🔍 Local Development

**Note**: Watson Orchestrator has host validation that prevents localhost usage. You'll see errors like:
- "Host validation failed"
- "Host is not supported"
- "Host is not in insights whitelist"

This is expected behavior. Deploy to a public domain to resolve.

## 🛠️ Troubleshooting

### Host Validation Errors
- **Problem**: "Host validation failed" on localhost
- **Solution**: Deploy to a public domain (Vercel, Netlify, etc.)

### Chat Not Loading
- Check browser console for errors
- Verify agent IDs are correct
- Ensure internet connection

### Processing Errors
- Verify agent configuration in IBM Watson
- Check if agent is active and properly set up
- Try different chat options

## 📊 Testing

1. **Local Test**: Open any HTML file in browser (expect host validation errors)
2. **Deployed Test**: Deploy to Vercel/Netlify and test chat functionality
3. **Debug Version**: Use `test-watson.html` for detailed logging

## 🎯 Usage

Once deployed to a public domain:
1. Open the deployed URL
2. Wait for Watson Orchestrator to load
3. Start chatting with the AI assistant
4. Enjoy the conversation!

## 📝 License

This project is for demonstration purposes. Watson Orchestrator is an IBM service.
