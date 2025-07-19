🛠️ Dev Aliases Cross-Platform

Este repositorio contiene mis configuraciones de alias personalizados para Git y desarrollo en diferentes entornos:

- 💻 PowerShell (Windows)
- 🍎 macOS (Zsh)
- 🐧 Linux (Bash)
- 🧰 Git Bash

## 📁 Estructura

- [`powershell/profile.ps1`](powershell/profile.ps1): Alias para PowerShell
- [`mac/.zshrc`](mac/.zshrc): Alias para macOS con Oh My Zsh
- [`gitbash/.bashrc`](gitbash/.bashrc): Alias para Git Bash
- [`linux/.bashrc`](linux/.bashrc): Alias para Linux
- [`docs/cheatsheet.md`](docs/cheatsheet.md): Documentación de todos los alias

## 📌 Alias destacados

### Git
```bash
gst   → git status
gpl   → git pull
gcom  → git commit -m
```

## 🚀 Instalación

### 💻 Windows (PowerShell)

1. **Localiza tu perfil de PowerShell:**
   ```powershell
   $PROFILE
   ```

2. **Si el archivo no existe, créalo:**
   ```powershell
   New-Item -Path $PROFILE -Type File -Force
   ```

3. **Copia el contenido del archivo [`powershell/profile.ps1`](powershell/profile.ps1) al final de tu perfil:**
   ```powershell
   notepad $PROFILE
   ```

4. **Reinicia PowerShell o recarga el perfil:**
   ```powershell
   . $PROFILE
   ```

5. **¡Listo!** Ahora puedes usar los alias como `gst`, `gpl`, `gcom`, etc.