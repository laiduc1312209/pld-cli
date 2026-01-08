# 📤 Pixeldrain CLI Tool

A beautiful and professional command-line tool for uploading and sharing files instantly using Pixeldrain. Features a gorgeous terminal UI with colors, loading animations, automatic clipboard integration, upload history tracking, and secure API key management.

## ✨ Features

- 🚀 **Fast uploads** with streaming support for large files
- 🎨 **Beautiful terminal UI** with colors and animations
- 📋 **Automatic clipboard** - download link copied instantly
- 📊 **Progress tracking** - see upload percentage in real-time
- 🔐 **Secure API key management** - stored locally in `~/.pld/`
- 📜 **Upload history** - track all your uploads
- 💾 **Memory efficient** - handles large files without issues
- 🛠️ **Professional CLI** - full command-line interface with Commander.js

## 📦 Installation

### Step 1: Install Dependencies

```bash
npm install
```

### Step 2: Link as Global Command

```bash
npm link
```

This makes the `pld` command available globally on your system.

### Step 3: Configure API Key

Get your free API key from Pixeldrain:

1. Create a free account at [Pixeldrain](https://pixeldrain.com)
2. Get your API key from [API Keys page](https://pixeldrain.com/user/api_keys)
3. Run the config command:

```bash
pld -config
```

4. Enter your API key when prompted

Your API key will be securely stored in `~/.pld/config.json`

## 🚀 Usage

### Available Commands

| Command | Description |
|---------|-------------|
| `pld -config` | Configure your Pixeldrain API key |
| `pld -s <file>` | Upload a file to Pixeldrain |
| `pld -h` | Show upload history (last 10 uploads) |
| `pld --help` | Display help and all available commands |

### Examples

#### Configure API Key (First time setup)
```bash
pld -config
```

#### Upload a file
```bash
pld -s document.pdf
```

#### Upload from any directory
```bash
pld -s C:\Users\Documents\image.png
```

#### Upload large files (with progress bar)
```bash
pld -s large-video.mp4
```

#### View upload history
```bash
pld -h
```

### Output Example

After a successful upload, you'll see:

```
┌─────────────────────────────────────┐
│   📤 Pixeldrain CLI Tool 📤        │
└─────────────────────────────────────┘

📁 File: document.pdf
📊 Size: 2.5 MB

✔ Upload complete! ✨

┌─────────────────────────────────────┐
│         Upload Successful! 🎉       │
└─────────────────────────────────────┘

🔗 Download Link:
   https://pixeldrain.com/u/abc123xyz

✓ Link copied to clipboard!
```

## 🗂️ File Structure

The tool creates a `.pld` directory in your home folder to store configuration and history:

```
~/.pld/
├── config.json    # Your API key (keep this secure!)
└── history.json   # Upload history (last 50 uploads)
```

## 🛠️ Technical Details

### Dependencies

- **axios** - HTTP client for API requests
- **form-data** - Multipart form data for file uploads
- **chalk** - Terminal color styling
- **ora** - Elegant terminal spinner
- **clipboardy** - Cross-platform clipboard access
- **commander** - Command-line interface framework

### API

This tool uses the [Pixeldrain API](https://pixeldrain.com/api) for file uploads. All uploads are authenticated using your API key via HTTP Basic Authentication.

### Security

- Your API key is stored locally in `~/.pld/config.json`
- Never share your config file with others
- The API key is never logged or displayed
- All uploads are encrypted in transit (HTTPS)

## 📝 Features in Detail

### Upload History

The tool automatically tracks your uploads and stores:
- Timestamp of upload
- Filename
- File size
- File ID
- Download link

View your history anytime with `pld -h`

### Progress Tracking

For large files, you'll see a real-time progress indicator:
```
⠹ Uploading... 45%
```

### Clipboard Integration

Every successful upload automatically copies the download link to your clipboard - just paste it anywhere!

## 🐛 Troubleshooting

### Command not found after `npm link`

Try running:
```bash
npm unlink
npm link
```

Or restart your terminal.

### Upload fails with 401/403 error

Your API key is invalid or expired. Reconfigure it:
```bash
pld -config
```

### Network errors

- Check your internet connection
- Verify Pixeldrain is accessible: https://pixeldrain.com
- Check if you're behind a proxy or firewall

### File not found

- Verify the file path is correct
- Use absolute paths for files outside the current directory
- Ensure the file exists and is readable

## 🎯 Roadmap

Future features planned:
- [ ] Multiple file upload support
- [ ] Custom expiry time for uploads
- [ ] Download files from Pixeldrain
- [ ] File encryption before upload
- [ ] Upload to custom folders/collections
- [ ] Export history to CSV

## 📄 License

MIT

---

Made with ❤️ for easy file sharing

**Get Started:** `pld -config`
