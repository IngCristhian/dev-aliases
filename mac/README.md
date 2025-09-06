# 🍎 Zsh Aliases - macOS

Configuración de alias personalizados para Zsh en macOS, optimizada para desarrollo con Git y Kubernetes usando Oh My Zsh.

## 📋 Requisitos

- macOS con Zsh (por defecto desde macOS Catalina)
- Git instalado (incluido con Xcode Command Line Tools)
- (Recomendado) Oh My Zsh instalado
- (Opcional) kubectl para alias de Kubernetes

## 🚀 Instalación

### Paso 1: Verificar Zsh

```bash
echo $SHELL
# Debería mostrar: /bin/zsh
```

### Paso 2: Instalar Oh My Zsh (Opcional pero Recomendado)

Si no tienes Oh My Zsh:
```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Paso 3: Configurar Aliases

#### Agregar Aliases al .zshrc

```bash
# Hacer backup del .zshrc actual
cp ~/.zshrc ~/.zshrc.backup

# Abrir .zshrc para editar
nano ~/.zshrc
# o si prefieres otro editor:
# code ~/.zshrc
# vim ~/.zshrc
```

Luego agrega exactamente este contenido al final del archivo:

```bash
# ===== ALIAS FUNCIONALES PARA GIT =====

alias gst='git status'
alias gpl='git pull'
alias gpu='git push'
alias gaa='git add .'
alias gcom='git commit -m'
alias gch='git checkout'
alias gb='git branch'
alias gcl='git clone'
alias gdf='git diff'
alias gft='git fetch origin'

# ===== ALIAS DE KUBECTL =====
alias k='kubectl'
alias kg='kubectl get'
alias kgp='kubectl get pods'
alias kgs='kubectl get svc'
alias kgd='kubectl get deployments'
alias kgn='kubectl get nodes'
alias kgcm='kubectl get configmap'
alias kgsec='kubectl get secret'
alias kgall='kubectl get all'
alias kctx='kubectl config current-context'
alias kdp='kubectl describe pod'
alias kl='kubectl logs'
alias klf='kubectl logs -f'
```

Guarda el archivo y recarga la configuración:
```bash
source ~/.zshrc
```

## 📌 Alias Disponibles

### Git Shortcuts
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `gst` | `git status` | Estado del repositorio |
| `gpl` | `git pull` | Obtener cambios remotos |
| `gpu` | `git push` | Enviar cambios al remoto |
| `gaa` | `git add .` | Agregar todos los archivos |
| `gcom` | `git commit -am` | Commit con mensaje |
| `gch` | `git checkout` | Cambiar rama o restaurar archivos |
| `gb` | `git branch` | Listar/gestionar ramas |
| `gcl` | `git clone` | Clonar repositorio |
| `gdf` | `git diff` | Ver diferencias |
| `gft` | `git fetch origin` | Obtener cambios sin merge |

### Kubernetes Shortcuts
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `k` | `kubectl` | Comando base de kubectl |
| `kg` | `kubectl get` | Obtener recursos |
| `kgp` | `kubectl get pods` | Listar pods |
| `kgs` | `kubectl get svc` | Listar servicios |
| `kgd` | `kubectl get deployments` | Listar deployments |
| `kgn` | `kubectl get nodes` | Listar nodos |
| `kgcm` | `kubectl get configmap` | Listar configmaps |
| `kgsec` | `kubectl get secret` | Listar secrets |
| `kgall` | `kubectl get all` | Listar todos los recursos |
| `kctx` | `kubectl config current-context` | Contexto actual |
| `kdp` | `kubectl describe pod` | Describir pod |
| `kl` | `kubectl logs` | Ver logs de pod |
| `klf` | `kubectl logs -f` | Ver logs en tiempo real |

## 🔧 Personalización

### Agregar Alias Personalizado

Edita tu `~/.zshrc`:
```bash
# Alias personalizado
alias myproject="cd ~/Documents/projects/mi-proyecto"
alias serve="python3 -m http.server 8000"
```

### Configurar Directorios de Proyecto

```bash
# Agregar al .zshrc
export PROJECTS_DIR="$HOME/Documents/projects"
alias projects="cd $PROJECTS_DIR"
```

## 🎨 Configuración Avanzada

### Habilitar Autocompletado Git

Si usas Oh My Zsh, agrega el plugin git:
```bash
# En ~/.zshrc
plugins=(git)
```

### Configurar Tema (Oh My Zsh)

```bash
# En ~/.zshrc
ZSH_THEME="agnoster"  # o tu tema preferido
```

## 🐛 Troubleshooting

### Verificar que Zsh está Configurado

```bash
# Verificar shell actual
echo $SHELL

# Cambiar a Zsh si es necesario
chsh -s /bin/zsh
```

### Alias No Funcionan

```bash
# Verificar si el alias existe
which gst

# Recargar configuración
source ~/.zshrc

# Verificar errores en .zshrc
zsh -n ~/.zshrc
```

### Restaurar Configuración Original

```bash
# Restaurar backup
cp ~/.zshrc.backup ~/.zshrc
source ~/.zshrc
```

### Problemas con Oh My Zsh

```bash
# Reinstalar Oh My Zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## 💡 Tips para macOS

- Usa `Command + T` para nueva pestaña en Terminal
- `Command + D` divide la pantalla en Terminal (con iTerm2)
- Instala iTerm2 para mejor experiencia: `brew install --cask iterm2`
- Configura autocompletado con `Tab`
- Usa `history | grep comando` para buscar en historial
- `Ctrl + R` para búsqueda reversa en historial
