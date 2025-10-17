# Watson Orchestrator Security Configuration Instructions

## 🎯 Goal: Disable Security to Fix Chat Interface

Your Watson Orchestrator chat interface is not working because security is enabled by default but not properly configured. We need to disable security to allow anonymous access.

## 📋 Prerequisites

1. **IBM watsonx Orchestrate instance** (you have this)
2. **API Key with administrative privileges** (you need this)
3. **Service Instance URL** from your watsonx Orchestrate instance (you need this)

## 🔍 How to Find Your API Details

1. **Log in to your watsonx Orchestrate instance**
2. **Click on the profile icon** in the top right corner
3. **Select "Settings"** from the dropdown menu
4. **Navigate to the "API Details" tab**
5. **Find the "Service instance URL"** field, which looks like:
   ```
   https://api.us-south.watson-orchestrate.ibm.com/instances/20250807-1007-4445-5049-459a42144389
   ```
6. **Your API URL** is the base URL: `https://api.us-south.watson-orchestrate.ibm.com`
7. **Your Instance ID** is the UUID after "/instances/": `20250807-1007-4445-5049-459a42144389`
8. **Your API Key** can also be found in the same API Details tab

## 🚀 Running the Security Tool

### On Windows (PowerShell):
```powershell
# The script will automatically detect Windows and run PowerShell version
./wxO-embed-chat-security-tool.sh
```

### On macOS/Linux (Bash):
```bash
# Make the script executable
chmod +x wxO-embed-chat-security-tool.sh

# Run the script
./wxO-embed-chat-security-tool.sh
```

## 📝 Step-by-Step Process

1. **Run the script** using one of the commands above
2. **Answer "y"** when asked if you need help finding your Service instance URL (if needed)
3. **Enter your Service instance URL** when prompted
4. **Enter your API Key** when prompted (it will be hidden for security)
5. **Select option "2"** - "Disable security and allow anonymous access"
6. **Type "yes"** to confirm you want to disable security
7. **Wait for the process to complete**

## ✅ Expected Results

After running the tool successfully:
- ✅ **Security will be disabled**
- ✅ **Anonymous access will be allowed**
- ✅ **Your chat interface will work** without host validation errors
- ✅ **You can send messages** and get responses from the AI

## 🔧 What This Does

The tool will:
1. **Connect to your Watson Orchestrator instance** using your API credentials
2. **Check current security configuration**
3. **Disable security** by setting `is_security_enabled: false`
4. **Clear any existing key pairs**
5. **Verify the configuration** was applied successfully

## 🎯 After Disabling Security

Once security is disabled:
1. **Refresh your Vercel deployment**: [https://watson-orchestrator-chat.vercel.app/](https://watson-orchestrator-chat.vercel.app/)
2. **The chat interface should work** without any errors
3. **You can send messages** and get AI responses
4. **No more "processing error"** messages

## ⚠️ Important Notes

- **This allows anonymous access** to your embedded chat
- **Only do this if your use case** requires anonymous access
- **Make sure your data and tools** are appropriate for anonymous access
- **You can re-enable security later** if needed

## 🆘 Troubleshooting

If you encounter issues:
1. **Check your API Key** - make sure it has administrative privileges
2. **Verify your Service instance URL** - it should include the full path with instance ID
3. **Try different environments** - the tool will automatically try Production, Development, and Test
4. **Run with verbose mode**: `./wxO-embed-chat-security-tool.sh -v`

## 📞 Need Help?

If you're still having issues:
1. **Check the console output** for specific error messages
2. **Verify your API credentials** in the Watson Orchestrator settings
3. **Make sure you have administrative access** to the instance
