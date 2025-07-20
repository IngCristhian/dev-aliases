# 💻 PowerShell Aliases - Windows

Configuración de alias personalizados para PowerShell en Windows, optimizada para desarrollo con Git y Kubernetes.

## 📋 Requisitos

- PowerShell 5.1 o superior (recomendado PowerShell 7+)
- Git instalado y configurado
- (Opcional) kubectl para alias de Kubernetes

## 🚀 Instalación

### Método 1: Instalación Automática

1. **Localiza tu perfil de PowerShell:**
   ```powershell
   $PROFILE
   ```

2. **Si el archivo no existe, créalo:**
   ```powershell
   New-Item -Path $PROFILE -Type File -Force
   ```

3. **Copia el contenido del archivo `profile.ps1` al final de tu perfil:**
   Abre el archivo con este comando:
   ```powershell
   notepad $PROFILE
   ```
   Luego copia y pega todo el contenido de `profile.ps1` guardalo y cierra el archivo.

4. **Reinicia PowerShell o recarga el perfil:**
   ```powershell
   . $PROFILE
   ```

### Método 2: Importación Directa

Alternativamente, puedes importar directamente desde el repositorio:

```powershell
# Navega al directorio del repositorio
cd "ruta/al/repositorio/dev-aliases/powershell"

# Importa los alias
. .\profile.ps1
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
| `glog` | `git log --oneline` | Log resumido |
| `gdiff` | `git diff` | Ver diferencias |

### Kubernetes Shortcuts
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `k` | `kubectl` | Comando base de kubectl |
| `kgp` | `kubectl get pods` | Listar pods |
| `kgs` | `kubectl get svc` | Listar servicios |
| `kgd` | `kubectl get deployments` | Listar deployments |
| `kdp` | `kubectl describe pod` | Describir pod |
| `klog` | `kubectl logs` | Ver logs de pod |

### Navegación y Utilidades
| Alias | Comando Original | Descripción |
|-------|------------------|-------------|
| `ll` | `Get-ChildItem` | Listar archivos detallado |
| `la` | `Get-ChildItem -Force` | Listar todos los archivos |
| `..` | `cd ..` | Subir un directorio |
| `...` | `cd ..\..` | Subir dos directorios |

## 🔧 Personalización

Para personalizar los alias:

1. **Edita el archivo `profile.ps1`** con tus alias preferidos
2. **Recarga el perfil:**
   ```powershell
   . $PROFILE
   ```

### Ejemplo de Alias Personalizado

```powershell
# Agregar al final de profile.ps1
function myproject { cd "C:\ruta\a\mi\proyecto" }
Set-Alias mp myproject
```

## 🐛 Troubleshooting

### Error de Política de Ejecución

Si recibes un error sobre políticas de ejecución:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### Verificar que los Alias Funcionan

```powershell
# Verificar que el alias existe
Get-Alias gst

# Listar todos los alias personalizados
Get-Alias | Where-Object { $_.Source -eq "" }
```

### Restaurar Configuración Original

Para remover los alias, simplemente elimina el contenido agregado de tu `$PROFILE` y reinicia PowerShell.

## 💡 Tips

- Usa `Tab` para autocompletado de comandos
- Los alias funcionan tanto en PowerShell como en PowerShell ISE
- Para ver todos los alias disponibles: `Get-Alias`
- Para encontrar tu perfil: `$PROFILE | Split-Path`