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

#### Método 1: Agregar al .bashrc existente

```bash
# Hacer backup del .bashrc actual
cp ~/.bashrc ~/.bashrc.backup

# Agregar los aliases al final del archivo
cat dev-aliases/linux/.bashrc >> ~/.bashrc

# Recargar configuración
source ~/.bashrc
```

#### Método 2: Reemplazar .bashrc (Solo si no tienes configuración previa)

```bash
# Hacer backup
cp ~/.bashrc ~/.bashrc.backup

# Copiar el archivo
cp dev-aliases/linux/.bashrc ~/.bashrc

# Recargar configuración
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
| `gps` | `git push` | Enviar cambios al remoto |
| `gco` | `git checkout` | Cambiar rama o restaurar archivos |
| `gcb` | `git checkout -b` | Crear y cambiar a nueva rama |
| `gcom` | `git commit -m` | Commit con mensaje |
| `gcam` | `git commit -am` | Add y commit con mensaje |
| `glog` | `git log --oneline --graph --all` | Log gráfico completo |
| `gdiff` | `git diff` | Ver diferencias |
| `gbr` | `git branch -v` | Listar ramas con detalles |

### Kubernetes Shortcuts
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `k` | `kubectl` | Comando base de kubectl |
| `kgp` | `kubectl get pods` | Listar pods |
| `kgs` | `kubectl get svc` | Listar servicios |
| `kgd` | `kubectl get deployments` | Listar deployments |
| `kgn` | `kubectl get nodes` | Listar nodos |
| `kga` | `kubectl get all` | Listar todos los recursos |
| `kdp` | `kubectl describe pod` | Describir pod |
| `klog` | `kubectl logs -f` | Ver logs en tiempo real |
| `kctx` | `kubectl config current-context` | Contexto actual |
| `kns` | `kubectl get namespaces` | Listar namespaces |

### Navegación y Utilidades Linux
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `ll` | `ls -la --color=auto` | Listar archivos detallado con colores |
| `la` | `ls -la --color=auto` | Listar todos los archivos |
| `l` | `ls -l --color=auto` | Listar archivos formato largo |
| `..` | `cd ..` | Subir un directorio |
| `...` | `cd ../..` | Subir dos directorios |
| `grep` | `grep --color=auto` | Grep con colores |
| `fgrep` | `fgrep --color=auto` | Fixed grep con colores |
| `egrep` | `egrep --color=auto` | Extended grep con colores |

### Sistema y Proceso
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `h` | `history` | Ver historial de comandos |
| `j` | `jobs -l` | Ver trabajos activos |
| `df` | `df -h` | Espacio en disco legible |
| `du` | `du -h` | Uso de directorio legible |
| `free` | `free -h` | Memoria disponible legible |
| `ps` | `ps aux` | Procesos detallados |

### Networking
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `ports` | `netstat -tuln` | Puertos abiertos |
| `myip` | `curl ifconfig.me` | IP pública |
| `localip` | `hostname -I` | IP local |

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