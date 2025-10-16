
# 🎙️ Voice Comment System (Free) - WordPress Plugin
[![WordPress](https://img.shields.io/badge/WordPress-5.0%2B-blue.svg)](https://wordpress.org/)
[![License](https://img.shields.io/badge/License-GPL%20v2-green.svg)](https://www.gnu.org/licenses/gpl-2.0.html)
[![Version](https://img.shields.io/badge/Version-1.0.0-orange.svg)]()
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)]()

**Let visitors record and submit voice comments using their browser microphone — completely FREE with no paid API required!**

![Voice Comment Demo](https://via.placeholder.com/800x400/667eea/ffffff?text=Voice+Comment+System+Demo)

---

## 🌟 Features

✨ **100% Free & Open Source** - No paid APIs, no subscriptions, no hidden costs  
🎤 **Browser-based Recording** - Uses native MediaRecorder API  
🗣️ **Auto Speech-to-Text** - Web Speech API for automatic transcription (Chrome/Edge)  
🌍 **Multi-language Support** - English, Bengali, Hindi, Spanish, and more  
🔒 **Secure** - Nonce verification, file size limits, input sanitization  
📱 **Responsive Design** - Works perfectly on desktop and mobile  
🎨 **Customizable** - Easy to style and modify  
🔧 **Shortcode Support** - `[voice_comment_form]` to add anywhere  
♻️ **Auto-delete** - Remove audio files when comments are deleted  
⚡ **No Dependencies** - Lightweight and fast

---

## 📸 Screenshots

### Recording Interface
![Recording Interface](https://via.placeholder.com/600x300/f8f9fa/333333?text=Recording+Interface)

### Comment Display
![Comment Display](https://via.placeholder.com/600x300/f8f9fa/333333?text=Voice+Comment+Display)

### Admin Settings
![Admin Settings](https://via.placeholder.com/600x300/f8f9fa/333333?text=Admin+Settings+Page)

---

## 🚀 Quick Start

### Installation

1. **Download the Plugin**
   ```bash
   git clone https://github.com/yourusername/voice-comment-system.git
   ```

2. **Upload to WordPress**
   - Upload the `voice-comment-system` folder to `/wp-content/plugins/`
   - Or zip the folder and upload via WordPress Admin

3. **Activate**
   - Go to **Plugins → Installed Plugins**
   - Click **Activate** on "Voice Comment System (Free)"

4. **Configure**
   - Navigate to **Settings → Voice Comments**
   - Adjust settings as needed
   - Click **Save Changes**

### Using Git

```bash
cd /path/to/wordpress/wp-content/plugins/
git clone https://github.com/yourusername/voice-comment-system.git
```

Then activate via WordPress admin panel.

---

## 📖 Usage

### Automatic Display

The voice recorder appears automatically below the comment form on all posts/pages where comments are enabled.

### Shortcode

Place this shortcode anywhere to display the voice recorder:

```
[voice_comment_form]
```

**Examples:**
- Inside Gutenberg blocks
- In page templates
- Widget areas
- Custom post types

---

## ⚙️ Configuration

Navigate to **Settings → Voice Comments** in your WordPress admin:

| Setting | Description | Default |
|---------|-------------|---------|
| **Max Recording Duration** | Maximum seconds users can record | 60 |
| **Enable Transcription** | Auto-convert speech to text | Yes |
| **Allowed Formats** | Audio file formats | webm,mp3,wav |
| **Auto-delete Audio** | Delete audio when comment deleted | Yes |
| **Require Login** | Only logged-in users can record | No |
| **Language** | Speech recognition language | en-US |

---

## 🎯 How It Works

### User Flow:
1. Click **"🎙 Record Voice Comment"**
2. Allow microphone access
3. Click **"Start Recording"**
4. Speak your comment (up to 60 seconds)
5. Click **"Stop Recording"**
6. Preview or re-record if needed
7. Submit comment

### Technical Flow:
1. **Recording:** MediaRecorder API captures audio
2. **Transcription:** Web Speech API converts speech to text
3. **Upload:** Audio encoded as base64 and sent via AJAX
4. **Storage:** Saved to `/wp-content/uploads/voice-comments/`
5. **Database:** Audio URL and transcript stored as comment meta
6. **Display:** Audio player and transcript shown with comment

---

## 🌐 Browser Compatibility

| Browser | Recording | Transcription |
|---------|-----------|---------------|
| Chrome | ✅ | ✅ |
| Edge | ✅ | ✅ |
| Firefox | ✅ | ❌ |
| Safari | ✅ | ❌ |
| Opera | ✅ | ✅ |

**Note:** Speech-to-text only works in Chromium-based browsers. Other browsers can still record audio.

---

## 🔒 Security Features

- ✅ **Nonce Verification** - All AJAX requests verified
- ✅ **File Size Limit** - Maximum 2MB per audio file
- ✅ **Input Sanitization** - All user inputs sanitized
- ✅ **File Type Validation** - Only audio formats accepted
- ✅ **Optional Login Requirement** - Restrict to authenticated users
- ✅ **XSS Prevention** - Output properly escaped

---

## 🛠️ Development

### File Structure

```
voice-comment-system/
├── voice-comment-system.php    # Main plugin file
├── uninstall.php                # Cleanup on deletion
├── README.md                    # Documentation
├── LICENSE                      # GPL v2 License
├── .gitignore                   # Git ignore rules
├── assets/
│   ├── css/
│   │   ├── style.css           # Frontend styles
│   │   └── index.php           # Security file
│   ├── js/
│   │   ├── recorder.js         # Recording logic
│   │   └── index.php           # Security file
│   └── images/                 # Screenshots (optional)
└── languages/                  # Translation files (future)
```

### Local Development

```bash
# Clone the repository
git clone https://github.com/yourusername/voice-comment-system.git

# Navigate to plugin directory
cd voice-comment-system

# Create a feature branch
git checkout -b feature/your-feature-name

# Make changes and commit
git add .
git commit -m "Add your feature"

# Push to GitHub
git push origin feature/your-feature-name
```

---

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

1. **Fork** the repository
2. Create a **feature branch** (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. Open a **Pull Request**

### Coding Standards
- Follow [WordPress Coding Standards](https://developer.wordpress.org/coding-standards/wordpress-coding-standards/)
- Use meaningful variable and function names
- Comment your code where necessary
- Test thoroughly before submitting PR

---

## 🐛 Bug Reports & Feature Requests

Found a bug or have a feature idea? 

- **Issues:** [GitHub Issues](https://github.com/yourusername/voice-comment-system/issues)
- **Discussions:** [GitHub Discussions](https://github.com/yourusername/voice-comment-system/discussions)

Please include:
- WordPress version
- PHP version
- Browser and version
- Steps to reproduce
- Expected vs actual behavior

---

## ❓ FAQ

### Does this work without internet?
No, the Web Speech API requires an internet connection for transcription. However, audio recording works offline.

### What's the maximum file size?
Default is 2MB. You can modify this in the plugin code if needed.

### Can I change the recording duration?
Yes, go to **Settings → Voice Comments** and adjust "Max Recording Duration".

### Does it work with custom comment forms?
Yes, but your theme must use the standard WordPress `comment_form()` function.

### How do I delete all voice files?
Simply deactivate and delete the plugin. The uninstall script will remove all files and data.

### Can I style the recorder interface?
Yes! Edit `assets/css/style.css` or override styles in your theme.

---

## 📝 Changelog

### Version 1.0.0 (2025-01-XX)
- 🎉 Initial release
- ✅ MediaRecorder API integration
- ✅ Web Speech API transcription
- ✅ Admin settings page
- ✅ Multi-language support
- ✅ Shortcode functionality
- ✅ Auto-delete feature
- ✅ Theme compatibility fixes

---

## 📜 License

This plugin is licensed under the **GPL v2 or later**.

```
Voice Comment System (Free)
Copyright (C) 2025  Your Name

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.
```

See [LICENSE](LICENSE) file for full text.

---

## 👤 Author

**Your Name**
- Website: [https://yourwebsite.com](https://yourwebsite.com)
- GitHub: [@yourusername](https://github.com/yourusername)
- Twitter: [@yourhandle](https://twitter.com/yourhandle)

---

## 🙏 Acknowledgments

- WordPress community for amazing documentation
- MediaRecorder API contributors
- Web Speech API developers
- All plugin testers and contributors

---

## ⭐ Show Your Support

If you found this plugin helpful, please:
- ⭐ Star this repository
- 🐛 Report bugs
- 💡 Suggest features
- 🔀 Submit pull requests
- 📢 Share with others

---

## 📞 Support

Need help? 

- 📖 [Documentation](https://github.com/yourusername/voice-comment-system/wiki)
- 💬 [Community Forum](https://github.com/yourusername/voice-comment-system/discussions)
- 📧 Email: support@yourwebsite.com

---

<p align="center">Made with ❤️ for the WordPress Community</p>

<p align="center">
  <a href="https://wordpress.org/">WordPress</a> •
  <a href="https://github.com/yourusername/voice-comment-system/issues">Report Bug</a> •
  <a href="https://github.com/yourusername/voice-comment-system/issues">Request Feature</a>
</p>
