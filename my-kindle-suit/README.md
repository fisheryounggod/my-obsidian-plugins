# Kindle Suite for Obsidian

📚 **Comprehensive Kindle integration** - Export notes to EPUB, send to Kindle, import highlights and vocabulary.

## ✨ Features

### 📤 Export
- **Export to EPUB** - Convert any Obsidian note to EPUB format
  - Markdown support with full formatting
  - WikiLinks images and standard images
  - LaTeX formulas (inline & display)
  - Custom metadata (title, author, cover)
  - Table of contents generation
  - **Mobile support** - Share EPUB on mobile devices

### 📧 Send to Kindle
- **Desktop**: Automatic SMTP email delivery
- **Mobile**: Open email app for manual sending
- Multiple Kindle device support
- Preview before sending
- Batch sending support

### 📥 Import
- **Import Kindle Notes** - From My Clippings.txt or HTML exports
  - File import or **clipboard import** (paste directly!)
  - Real-time preview
  - Smart duplicate handling
  - Organizes by book
  - Daily notes integration

- **Import Vocabulary** - From Kindle vocabulary files
  - CSV/TXT vocabulary files
  - Fully customizable templates
  - YAML or Markdown format
  - Organized by word and book

### 🌟 Platform Support
- ✅ **Desktop** (Windows, macOS, Linux)
- ✅ **Mobile** (iOS, Android)
- 🔄 **Automatic fallback** - Uses appropriate method for each platform

## 📦 Installation

### Method 1: Manual Install

1. Download the latest release from [Releases](https://github.com/yourusername/obsidian-kindle-suite/releases)
2. Extract to your Obsidian vault: `vault/.obsidian/plugins/obsidian-kindle-suite/`
3. Reload Obsidian or enable Community Plugins
4. Enable "Kindle Suite" in plugin settings

### Method 2: Build from Source

```bash
# Clone or download the repository
cd obsidian-kindle-suite

# Install dependencies
npm install

# Build the plugin
npm run build
```

The built files will be in the plugin directory, ready to use.

## ⚙️ Configuration

### 📧 SMTP Settings (Desktop Only)

Configure SMTP to send emails directly to Kindle:

1. Open plugin settings
2. Under **SMTP Configuration**:
   - **Host**: `smtp.gmail.com` (or your SMTP server)
   - **Port**: `587` (TLS) or `465` (SSL)
   - **Username**: Your email address
   - **Password**: Your email password or **app password**

**Gmail Users**: Generate an app password:
1. Google Account → Security → 2-Step Verification
2. App passwords → Generate
3. Use the 16-character password instead of your regular password

### 📱 Email Presets

Configure Kindle device presets for quick sending:

1. Under **Email Presets**, click "Add Email Preset"
2. Set:
   - **Name**: Device name (e.g., "My Kindle Paperwhite")
   - **Kindle Email**: Found at [Amazon](https://www.amazon.com/sendtokindle)
   - **From Email**: Your approved email address

### 📁 Folder Paths

Customize import/export locations (default paths shown):

- `Kindle Imports/` - Imported Kindle notes and highlights
- `Kindle Vocabulary/` - Imported vocabulary words
- `EPUB Exports/` - Generated EPUB files

### 🎨 Templates

Customize how imported content is formatted:

#### Note Template
Template for individual book note files. Placeholders:
- `{{title}}` - Book title
- `{{author}}` - Author name
- `{{highlights}}` - All highlights content
- `{{noteCount}}` - Number of highlights/notes
- `{{firstRead}}` - First reading date
- `{{lastRead}}` - Last reading date
- `{{importDate}}` - Import date
- `{{summary}}` - Book citation/info

#### Highlights Template
Template for each highlight/note entry. Placeholders:
- `{{content}}` - Highlight/note text
- `{{location}}` - Location in book
- `{{date}}` - Full date string
- `{{dateShort}}` - Short date (YYYYMMDD)
- `{{dateTime}}` - Date-time (YYYYMMDDHHmm)
- `{{color}}` - Highlight color

#### Daily Note Entry Template
For daily notes integration. Placeholders:
- `{{time}}` - Time (HH:mm)
- `{{color}}` - Highlight color
- `{{content}}` - Content
- `{{title}}` - Book title
- `{{author}}` - Author

#### Vocabulary Templates
- **Vocabulary File Template** - Overall file structure
- **Vocabulary Word Template** - Each word entry format
- **Placeholders**: `{{word}}`, `{{usage}}`, `{{bookTitle}}`, `{{date}}`, `{{importDate}}`, `{{wordCount}}`

## 📖 Supported Import Formats

### Kindle Notes (My Clippings.txt)

The standard format from Kindle e-ink devices:

```
书名 (作者)
- 您的笔记或高亮内容
- 另一条笔记
==========
Book Title (Author)
- Your highlight or note
- Another highlight
==========
```

**Format Specification:**
- Each book section starts with `书名 (作者)` or `Book Title (Author)`
- Notes/highlights start with `- `
- Book sections are separated by `==========`

**Example:**
```
人类简史 (尤瓦尔·赫拉利)
- 认知革命让我非常震撼，完全颠覆了我对历史的认知。
- 智人设计理论很有趣，但也存在一些争议。
==========
Thinking, Fast and Slow (Daniel Kahneman)
- System 1 is fast, intuitive, and emotional.
- System 2 is slower, more deliberative, and logical.
==========
```

### Kindle iOS HTML Exports

HTML files exported from the Kindle iOS app are automatically parsed.

### Vocabulary Files

#### CSV/TXT Format
Simple text or CSV files with vocabulary:

```
word,usage,book_title
serendipity,"The occurrence of events by chance",The Alchemist
ephemeral,"Lasting for a very short time",Word Power Made Easy
```

#### Custom Format
Use any delimiter and customize the vocabulary template to match.

## 🚀 Usage

### Export to EPUB

#### Desktop
1. Open any note in Obsidian
2. Press `Ctrl/Cmd + P` → "Kindle: Export current note to EPUB"
3. Edit metadata if needed
4. Click "Export"
5. EPUB saved to `EPUB Exports/` folder

#### Mobile
1. Open a note
2. Use "Export to EPUB" command
3. Edit metadata
4. Click "Export & Share"
5. Choose share destination (Files, etc.)

### Send to Kindle

#### Desktop (Automatic)
1. Open a note
2. `Ctrl/Cmd + P` → "Kindle: Send current note to Kindle"
3. Select Kindle device
4. Click "Send"
5. ✅ EPUB appears on your Kindle in 5-10 minutes

#### Mobile (Manual)
1. Open a note
2. Use "Send to Kindle" command
3. Enter Kindle email
4. Click "Generate & Open Email App"
5. Attach the generated EPUB
6. Send email

### Import Kindle Notes

#### File Import
1. Connect Kindle via USB or use Kindle app
2. Find `My Clippings.txt` (e-ink) or export HTML (iOS)
3. `Ctrl/Cmd + P` → "Kindle: Import Kindle Notes"
4. Select import method: **📁 File Import**
5. Choose file
6. Preview and click "导入"

#### Clipboard Import ✨
1. Open `My Clippings.txt` on your computer
2. `Ctrl+A` to select all, `Ctrl+C` to copy
3. In Obsidian: `Ctrl/Cmd + P` → "Kindle: Import Kindle Notes"
4. Select **📋 剪贴板导入**
5. Click "📋 从剪贴板粘贴" (or manually paste)
6. Real-time preview appears
7. Click "导入"

**Tips for Clipboard Import:**
- Perfect for mobile users
- No file transfer needed
- Works with copy from any source
- Validates format before import

### Import Vocabulary

1. Export vocabulary from Kindle/app
2. `Ctrl/Cmd + P` → "Kindle: Import Kindle Vocabulary"
3. Select vocabulary file (CSV/TXT)
4. Choose import format
5. Click "Import"
6. Vocabulary saved to `Kindle Vocabulary/vocabulary.md`

### Send EPUB to Kindle

#### Desktop
1. `Ctrl/Cmd + P` → "Kindle: Send EPUB to Kindle"
2. Choose EPUB file
3. Select device
4. Click "Send"

#### Mobile
1. Use "Send EPUB to Kindle" command
2. Select EPUB file
3. Enter Kindle email
4. Click "Open Email App"
5. Attach file and send

## 📝 Note Frontmatter

Control EPUB metadata with frontmatter:

```yaml
---
title: My Book Title
author: Author Name
cover: path/to/cover-image.png
language: en
---

# Your Content

Your note content here...
```

## 🎨 Template Examples

### Minimal Note Template
```markdown
# {{title}}

## Highlights

{{highlights}}
```

### Detailed Note Template
```markdown
---
title: {{title}}
author: {{author}}
tags: [kindle, reading]
read: {{firstRead}}
---

# {{title}}

By {{author}}

> Imported on {{importDate}}
> {{summary}}

## Reading Statistics

- Notes: {{noteCount}}
- First read: {{firstRead}}
- Last read: {{lastRead}}

## Highlights

{{highlights}}
```

### Flashcard-Style Highlights
```markdown
- #{{color}} {{content}}
  - [[{{dateShort}}|{{dateTime}}]]
```

### Daily Notes Format
```markdown
## 📚 Reading

### Kindle

{{content}}
```

## 📱 Mobile vs Desktop Features

| Feature | Desktop | Mobile |
|---------|---------|--------|
| **Export to EPUB** | ✅ Save to file | ✅ Share dialog |
| **Send to Kindle** | ✅ SMTP email | ✅ Email app |
| **Import Notes** | ✅ File + Clipboard | ✅ File + Clipboard |
| **Import Vocabulary** | ✅ Full support | ✅ Full support |
| **SMTP Configuration** | ✅ Full settings | ⚠️ Not needed |

## 🔧 Troubleshooting

### Email sending fails (Desktop)
- Verify SMTP settings are correct
- Check if using app password (Gmail)
- Try port 465 with SSL enabled
- Check firewall/antivirus isn't blocking SMTP

### Can't enable plugin on mobile
- Ensure `isDesktopOnly: false` in manifest.json
- Update to latest plugin version
- Check Obsidian Mobile is up to date

### Import shows no content
- Verify file format matches specification
- Try importing via clipboard to test format
- Check for special characters in file

### Clipboard paste not working
- Manually copy/paste instead of using the button
- Check browser clipboard permissions
- Try shorter content first

## 🛠️ Development

```bash
# Install dependencies
npm install

# Development build with watch mode
npm run dev

# Production build
npm run build

# Version bump
npm run version
```

## 📂 Project Structure

```
obsidian-kindle-suite/
├── main.ts                    # Plugin entry point
├── types.ts                   # Type definitions
├── modules/                   # Core utilities
│   ├── epub-generator.ts      # EPUB creation
│   ├── email-client.ts        # SMTP/email handling
│   ├── folder-manager.ts      # File operations
│   └── kindle-parser.ts       # Kindle file parsing
├── features/                  # Feature implementations
│   ├── note-exporter.ts       # Export notes to EPUB
│   ├── note-sender.ts         # Send notes to Kindle
│   ├── notes-importer.ts      # Import Kindle notes
│   ├── vocabulary-importer.ts # Import vocabulary
│   └── epub-sender.ts         # Send EPUB files
├── styles.css                  # Plugin styles
├── manifest.json               # Plugin manifest
└── package.json               # NPM configuration
```

## 🗺️ Roadmap

### Completed ✅
- [x] EPUB export with mobile sharing
- [x] Desktop SMTP email sending
- [x] Mobile email app fallback
- [x] My Clippings.txt import
- [x] Kindle iOS HTML import
- [x] **Clipboard import** (NEW!)
- [x] Vocabulary import with templates
- [x] Daily notes integration
- [x] Customizable templates
- [x] iOS and Android support

### Future Plans 📋
- [ ] Vocabulary Anki export
- [ ] Batch operations
- [ ] Import history tracking
- [] Cloud storage integration
- [ ] Enhanced image processing
- [ ] Direct Kindle API integration

## 🙏 Credits

Consolidates and enhances functionality from:
- obsidian-epub-export
- obsidian-send-to-kindle
- kindle-import-plugin
- obsidian-kindle-vocabulary

## 📄 License

MIT License - feel free to use, modify, and distribute

## 🤝 Contributing

Contributions welcome! Please feel free to:
- Report bugs
- Suggest new features
- Submit pull requests
- Improve documentation

## 📞 Support

- Issues: [GitHub Issues](https://github.com/yourusername/obsidian-kindle-suite/issues)
- Discussions: [GitHub Discussions](https://github.com/yourusername/obsidian-kindle-suite/discussions)

---

**Made with ❤️ for readers and knowledge management enthusiasts**
