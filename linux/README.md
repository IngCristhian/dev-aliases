# 🐧 Bash Aliases - Linux

Configuración de alias personalizados para Bash en distribuciones Linux, optimizada para desarrollo con Git y Kubernetes.

## 📋 Requisitos

- Linux con Bash (disponible en todas las distribuciones principales)
- Git instalado
- (Opcional) kubectl para alias de Kubernetes

### Instalación de Dependencias

#### Ubuntu/Debian:
```bash
sudo apt update
sudo apt install git curl
```

#### CentOS/RHEL/Fedora:
```bash
# CentOS/RHEL
sudo yum install git curl

# Fedora
sudo dnf install git curl
```

#### Arch Linux:
```bash
sudo pacman -S git curl
```

## 🚀 Instalación

### Paso 1: Verificar Bash

```bash
echo $SHELL
# Debería mostrar: /bin/bash
```

### Paso 2: Configurar Aliases

#### Agregar Aliases al .bashrc

```bash
# Hacer backup del .bashrc actual
cp ~/.bashrc ~/.bashrc.backup

# Abrir .bashrc para editar
nano ~/.bashrc
# o si prefieres otro editor:
# vim ~/.bashrc
# code ~/.bashrc  # si tienes VS Code instalado
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
source ~/.bashrc
```

### Paso 3: Verificar Instalación

```bash
# Verificar que los alias funcionan
gst
# Debería ejecutar: git status
```

## 📌 Alias Disponibles

### Git Shortcuts
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `gst` | `git status` | Estado del repositorio |
| `gpl` | `git pull` | Obtener cambios remotos |
| `gpu` | `git push` | Enviar cambios al remoto |
| `gaa` | `git add .` | Agregar todos los archivos |
| `gcom` | `git commit -m` | Commit con mensaje |
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

Edita tu `~/.bashrc`:
```bash
# Alias personalizado para proyectos
alias myproject="cd ~/projects/mi-proyecto"
alias serve="python3 -m http.server 8000"

# Alias para Docker (si lo usas)
alias dps="docker ps"
alias dimg="docker images"
```

### Configurar Variables de Entorno

```bash
# Agregar al .bashrc
export PROJECTS_DIR="$HOME/projects"
export EDITOR="nano"  # o tu editor preferido
```

## 🎨 Configuración Avanzada

### Habilitar Autocompletado Git

```bash
# Ubuntu/Debian
sudo apt install bash-completion

# Agregar a .bashrc
if [ -f /etc/bash_completion ] && ! shopt -oq posix; then
    . /etc/bash_completion
fi
```

### Personalizar Prompt

```bash
# Agregar al .bashrc para un prompt colorido
export PS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
```

### Habilitar Historial Mejorado

```bash
# Agregar al .bashrc
export HISTSIZE=10000
export HISTFILESIZE=20000
export HISTCONTROL=ignoredups:erasedups
shopt -s histappend
```

## 🐛 Troubleshooting

### Alias No Funcionan

```bash
# Verificar si el alias existe
type gst

# Recargar configuración
source ~/.bashrc

# Verificar errores en .bashrc
bash -n ~/.bashrc
```

### Problemas de Permisos

```bash
# Verificar permisos del .bashrc
ls -la ~/.bashrc

# Corregir permisos si es necesario
chmod 644 ~/.bashrc
```

### Restaurar Configuración Original

```bash
# Restaurar backup
cp ~/.bashrc.backup ~/.bashrc
source ~/.bashrc
```

### Comando No Encontrado

```bash
# Verificar si Git está instalado
git --version

# Instalar Git si es necesario
sudo apt install git  # Ubuntu/Debian
```

## 💡 Tips para Linux

- Usa `Ctrl + R` para búsqueda reversa en historial
- `Ctrl + L` limpia la pantalla
- `Tab` para autocompletado
- `!!` ejecuta el último comando
- `!$` usa el último argumento del comando anterior
- `history | grep comando` para buscar en historial
- Usa `screen` o `tmux` para sesiones persistentes
- `which comando` para encontrar ubicación de comandos