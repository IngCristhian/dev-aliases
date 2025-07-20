# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a cross-platform development aliases repository containing shell configurations for different environments:
- PowerShell (Windows): `powershell/profile.ps1`
- Zsh (macOS): `mac/.zshrc`  
- Bash (Linux): `linux/.bashrc`
- Git Bash: `gitbash/.bashrc`

The repository provides consistent development aliases across platforms, primarily focused on Git shortcuts and common development commands.

## Architecture

The repository follows a platform-based organization with self-contained folders:
```
dev-aliases/
├── powershell/              # Windows PowerShell configuration
│   ├── profile.ps1         # PowerShell aliases
│   └── README.md           # Windows-specific installation guide
├── mac/                    # macOS configuration
│   ├── .zshrc             # Zsh aliases
│   └── README.md          # macOS-specific installation guide
├── linux/                 # Linux configuration
│   ├── .bashrc            # Bash aliases
│   └── README.md          # Linux-specific installation guide
├── gitbash/               # Git Bash configuration
│   ├── .bashrc            # Git Bash aliases
│   └── README.md          # Git Bash-specific installation guide
└── README.md              # Main repository overview
```

Each platform folder is self-contained with its own documentation and installation instructions.

## Common Operations

Since this is a configuration repository without build tools:

- **View aliases**: Check the configuration file in each platform folder
- **Read instructions**: Each folder has its own README.md with detailed setup steps
- **Test changes**: Source the configuration file manually in your shell
- **Validate syntax**: Use platform-specific syntax checkers (e.g., `powershell -NoProfile -Command "& { . ./powershell/profile.ps1 }"`)

## Key Alias Categories

Based on the README, the main alias categories include:
- **Git shortcuts**: `gst` (git status), `gpl` (git pull), `gcom` (git commit -m)
- **Navigation utilities**: Directory and file system shortcuts
- **Development workflow**: Platform-specific development tools and commands

## Installation Process

Each platform has its own detailed installation guide:
- **Windows**: See `powershell/README.md` for PowerShell profile setup
- **macOS**: See `mac/README.md` for Zsh configuration
- **Linux**: See `linux/README.md` for Bash setup
- **Git Bash**: See `gitbash/README.md` for Git Bash configuration

All installations require manual sourcing or shell restart after setup.