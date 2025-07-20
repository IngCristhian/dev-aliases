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

#### Método 1: Agregarlo al .zshrc

```bash
# Hacer backup del .zshrc actual
cp ~/.zshrc ~/.zshrc.backup

# Agregar los aliases al final del archivo
cat dev-aliases/mac/.zshrc >> ~/.zshrc

# Recargar configuración
source ~/.zshrc
```

#### Método 2: Reemplazar .zshrc (Solo si no tienes configuración previa)

```bash
# Hacer backup
cp ~/.zshrc ~/.zshrc.backup

# Copiar el archivo
cp dev-aliases/mac/.zshrc ~/.zshrc

# Recargar configuración
source ~/.zshrc
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

### Navegación y Utilidades macOS
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `ll` | `ls -la` | Listar archivos detallado |
| `la` | `ls -la` | Listar todos los archivos |
| `..` | `cd ..` | Subir un directorio |
| `...` | `cd ../..` | Subir dos directorios |
| `finder` | `open .` | Abrir directorio actual en Finder |
| `code.` | `code .` | Abrir directorio en VS Code |

### Homebrew Shortcuts
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `br` | `brew` | Comando base de Homebrew |
| `bri` | `brew install` | Instalar paquete |
| `bru` | `brew update && brew upgrade` | Actualizar Homebrew y paquetes |
| `brs` | `brew search` | Buscar paquete |

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