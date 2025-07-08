# Auto-Commit GitHub Bot 🤖

An automated JavaScript program that creates daily commits to maintain your GitHub activity streak with desktop shortcut support.

## ✨ Features
- 🎯 **Smart Commit Patterns**: Creates "AVII" pattern in your GitHub activity graph
- 📝 **Random Content Generation**: Generates meaningful daily activity logs
- 🚀 **One-Click Setup**: Automated setup script for easy configuration
- 🖥️ **Desktop Shortcut**: Create shortcuts for quick access
- 🔄 **Cross-Platform**: Works on Windows, macOS, and Linux
- 🔒 **Safe & Secure**: No sensitive data committed
- 📊 **Customizable**: Easy to modify commit patterns and messages

## 🚀 Quick Start

### Prerequisites
- [Node.js](https://nodejs.org/) (version 12 or higher)
- [Git](https://git-scm.com/)
- GitHub account

### Installation

1. **Clone this repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/auto-commit.git
   cd auto-commit
   ```

2. **Run the automated setup**
   ```bash
   npm run setup
   ```
   
   This will:
   - Check prerequisites
   - Configure Git settings
   - Set up remote repository
   - Test the script

3. **Create a desktop shortcut** (optional)
   ```bash
   npm run create-shortcut
   ```

## 📖 Manual Setup (Alternative)

### 1. Create GitHub Repository
1. Go to [GitHub.com](https://github.com) and sign in
2. Click the "+" icon → "New repository"
3. Name it "auto-commit" or similar
4. Make it **Public** (for GitHub activity to show)
5. Click "Create repository"

### 2. Configure Git
```bash
# Initialize git (if not already done)
git init

# Add your GitHub repository as origin
git remote add origin https://github.com/YOUR_USERNAME/auto-commit.git

# Set up your git credentials
git config user.name "Your Name"
git config user.email "your.email@example.com"
```

### 3. Test the Script
```bash
# Run once to test
npm start
```

## 🎮 Usage

### Quick Commands
```bash
npm start          # Make a commit now
npm run setup      # Run setup wizard
npm run commit     # Alternative commit command
npm run create-shortcut  # Create desktop shortcut
```

### Desktop Shortcut
After running `npm run create-shortcut`, you'll have a desktop icon that:
- Runs the auto-commit script with one click
- Works on Windows, macOS, and Linux
- Shows progress in a terminal window

## 🔄 Automation Options

### Option 1: Windows Task Scheduler
1. Open Task Scheduler
2. Create Basic Task → "Daily GitHub Commit"
3. Set trigger to Daily
4. Action: Start a program
5. Program: `node`
6. Arguments: `daily-commit.js`
7. Start in: Your project directory

### Option 2: GitHub Actions (Recommended)
Create `.github/workflows/daily-commit.yml`:

```yaml
name: Daily Commit
on:
  schedule:
    - cron: '0 12 * * *'  # Daily at 12 PM UTC
  workflow_dispatch:

jobs:
  commit:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
      - name: Make daily commit
        run: |
          git config user.name "GitHub Actions Bot"
          git config user.email "actions@github.com"
          node daily-commit.js
```

### Option 3: Cron Job (Linux/macOS)
```bash
# Edit crontab
crontab -e

# Add this line for daily execution at 12 PM
0 12 * * * cd /path/to/auto-commit && node daily-commit.js
```

## 📊 How It Works

1. **Pattern Generation**: Creates an "AVII" pattern in your GitHub activity graph
2. **Content Creation**: Generates random daily activity logs
3. **Git Operations**: Commits and pushes changes automatically
4. **Smart Commits**: Varies commit frequency based on the pattern

## 📁 Files Created
- `daily-activity.txt` - Random daily activity logs
- `automation-log.txt` - Script execution logs
- Git commit history with meaningful messages

## 🛠️ Customization

### Modify Commit Messages
Edit the `commitMessages` array in `daily-commit.js`:

```javascript
const commitMessages = [
    'Your custom message 1',
    'Your custom message 2',
    // Add more messages...
];
```

### Change Activity Pattern
Modify the `AVII_PATTERN` object to create different GitHub activity patterns.

### Adjust Commit Frequency
Change the `getCommitCount()` function to modify how many commits are made per day.

## 🔧 Troubleshooting

### Common Issues

**"Not in a git repository"**
- The script will initialize git automatically
- Or run: `git init`

**"Could not push to remote"**
- Check if remote is configured: `git remote -v`
- Add remote: `git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git`

**"Authentication failed"**
- Use Personal Access Token instead of password
- Or set up SSH keys: [GitHub SSH Guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

**"Command not found: node"**
- Install Node.js from [nodejs.org](https://nodejs.org/)
- Restart your terminal after installation

**"Permission denied"**
- On Linux/macOS: Check file permissions
- Make scripts executable: `chmod +x filename`

### Getting Help

If you encounter issues:
1. Run `npm run setup` to reconfigure
2. Check the troubleshooting section above
3. Ensure Node.js and Git are properly installed
4. Verify your GitHub repository is accessible

## 🔒 Security & Privacy

- ✅ No sensitive data is committed
- ✅ Only creates harmless text files
- ✅ No external dependencies beyond Node.js built-ins
- ✅ Safe to run automatically
- ✅ Open source - you can review all code

## 📄 License

MIT License - Feel free to modify and use as needed!

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues.

## ⭐ Show Your Support

If this project helped you, please give it a star! ⭐
