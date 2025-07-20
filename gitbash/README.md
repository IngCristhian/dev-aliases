# 🧰 Git Bash Aliases - Windows

Configuración de alias personalizados para Git Bash en Windows, optimizada para desarrollo con Git y Kubernetes.

## 📋 Requisitos

- Git for Windows instalado (incluye Git Bash)
- (Opcional) kubectl para alias de Kubernetes
- Windows 10 o superior

### Instalación de Git for Windows

Si no tienes Git Bash:
1. Descarga Git for Windows desde: https://git-scm.com/download/win
2. Ejecuta el instalador con las opciones por defecto
3. Git Bash estará disponible en el menú de inicio

## 🚀 Instalación

### Paso 1: Abrir Git Bash

- Busca "Git Bash" en el menú de inicio, o
- Click derecho en cualquier carpeta → "Git Bash Here"

### Paso 2: Configurar Aliases

#### Método 1: Agregar al .bashrc existente

```bash
# Verificar si existe .bashrc en tu home
ls -la ~/ | grep bashrc

# Si existe, hacer backup
cp ~/.bashrc ~/.bashrc.backup

# Agregar los aliases
cat /c/ruta/a/dev-aliases/gitbash/.bashrc >> ~/.bashrc

# Recargar configuración
source ~/.bashrc
```

#### Método 2: Crear .bashrc nuevo

```bash
# Copiar el archivo de configuración
cp /c/ruta/a/dev-aliases/gitbash/.bashrc ~/.bashrc

# Recargar configuración
source ~/.bashrc
```

### Paso 3: Hacer la Configuración Persistente

Para que los alias estén disponibles en cada sesión:

```bash
# Verificar que .bashrc se carga automáticamente
echo 'source ~/.bashrc' >> ~/.bash_profile
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
| `glog` | `git log --oneline --graph` | Log gráfico resumido |
| `gdiff` | `git diff` | Ver diferencias |
| `gbr` | `git branch` | Listar ramas |
| `gadd` | `git add .` | Agregar todos los archivos |

### Kubernetes Shortcuts
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `k` | `kubectl` | Comando base de kubectl |
| `kgp` | `kubectl get pods` | Listar pods |
| `kgs` | `kubectl get svc` | Listar servicios |
| `kgd` | `kubectl get deployments` | Listar deployments |
| `kgn` | `kubectl get nodes` | Listar nodos |
| `kdp` | `kubectl describe pod` | Describir pod |
| `klog` | `kubectl logs -f` | Ver logs en tiempo real |
| `kctx` | `kubectl config current-context` | Contexto actual |

### Navegación Windows-Friendly
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `ll` | `ls -la` | Listar archivos detallado |
| `la` | `ls -la` | Listar todos los archivos |
| `..` | `cd ..` | Subir un directorio |
| `...` | `cd ../..` | Subir dos directorios |
| `home` | `cd ~` | Ir al directorio home |
| `desktop` | `cd ~/Desktop` | Ir al escritorio |
| `downloads` | `cd ~/Downloads` | Ir a descargas |

### Utilidades Windows
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `explorer` | `explorer.exe .` | Abrir explorador en directorio actual |
| `notepad` | `notepad.exe` | Abrir Notepad |
| `code.` | `code .` | Abrir VS Code en directorio actual |

### Docker Shortcuts (si está instalado)
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `dps` | `docker ps` | Contenedores activos |
| `dimg` | `docker images` | Listar imágenes |
| `dstop` | `docker stop $(docker ps -q)` | Parar todos los contenedores |

## 🔧 Personalización

### Agregar Alias Personalizado

Edita tu `~/.bashrc`:
```bash
# Alias para navegación rápida a proyectos
alias projects="cd /c/Users/$USER/Documents/Projects"
alias myproject="cd /c/ruta/a/mi/proyecto"

# Alias para herramientas
alias python="python.exe"
alias node="node.exe"
```

### Configurar Variables de Entorno

```bash
# Agregar al .bashrc
export PROJECTS_DIR="/c/Users/$USER/Documents/Projects"
export EDITOR="code"
```

## 🎨 Configuración Avanzada

### Personalizar Prompt

```bash
# Agregar al .bashrc para un prompt colorido
export PS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
```

### Habilitar Autocompletado

Git Bash viene con autocompletado de Git habilitado por defecto. Para otros comandos:

```bash
# Verificar que funciona
git <TAB><TAB>  # Debería mostrar opciones
```

### Configurar Historial

```bash
# Agregar al .bashrc
export HISTSIZE=5000
export HISTFILESIZE=10000
shopt -s histappend
```

## 🐛 Troubleshooting

### Alias No Funcionan

```bash
# Verificar si el alias existe
type gst

# Recargar configuración
source ~/.bashrc

# Verificar si .bashrc tiene errores
bash -n ~/.bashrc
```

### Problema con Rutas de Windows

Git Bash usa rutas Unix. Para convertir:
```bash
# Ruta Windows: C:\Users\usuario\Documents
# Ruta Git Bash: /c/Users/usuario/Documents

# Convertir automáticamente
cygpath -u "C:\Users\usuario\Documents"
```

### .bashrc No Se Carga Automáticamente

```bash
# Verificar si existe .bash_profile
ls -la ~/ | grep bash_profile

# Si no existe, crear uno
echo 'source ~/.bashrc' > ~/.bash_profile

# Si existe, agregar la línea
echo 'source ~/.bashrc' >> ~/.bash_profile
```

### Problemas de Permisos

```bash
# Verificar permisos
ls -la ~/.bashrc

# Corregir si es necesario
chmod 644 ~/.bashrc
```

### Restaurar Configuración Original

```bash
# Restaurar backup
cp ~/.bashrc.backup ~/.bashrc
source ~/.bashrc

# O eliminar completamente
rm ~/.bashrc
```

## 💡 Tips para Git Bash

- **Ctrl + Shift + C/V**: Copiar/Pegar (o click derecho)
- **Ctrl + L**: Limpiar pantalla
- **Tab**: Autocompletado
- **Ctrl + R**: Búsqueda reversa en historial
- **Click derecho**: Menú contextual con opciones
- **Shift + Click**: Seleccionar texto
- **Ctrl + Plus/Minus**: Zoom in/out
- **Alt + Enter**: Pantalla completa

### Integración con Windows

```bash
# Abrir archivo con aplicación por defecto de Windows
start archivo.txt

# Abrir URL en navegador por defecto
start https://github.com

# Ejecutar comando de Windows
cmd //c "comando de windows"
```

### Trucos de Productividad

```bash
# Navegación rápida entre drives
alias c:="cd /c"
alias d:="cd /d"

# Ver historial con números
alias h="history | tail -20"

# Limpiar pantalla y mostrar ubicación
alias cls="clear && pwd"
```