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

3. **Copia y pega el siguiente contenido al final de tu perfil:**
   
   Abre el archivo con este comando:

   ```powershell
   notepad $PROFILE
   ```
   
   Luego copia y pega exactamente este contenido:

   ```powershell
   # ===== ALIAS FUNCIONALES PARA GIT (con Function) =====
   
   Function gst  { git status }
   Function gpl  { git pull }
   Function gpu  { git push }
   Function gaa  { git add . }
   Function gcom { git commit -m @args }
   Function gch  { git checkout @args }
   Function gb   { git branch }
   Function gcl  { git clone @args }
   Function gdf  { git diff }
   Function gft  { git fetch origin }
   
   # ===== ALIAS DE KUBECTL =====
   Set-Alias k kubectl
   Set-Alias kubectl kubectl
   Set-Alias kg "kubectl get"
   Set-Alias kgp "kubectl get pods"
   Set-Alias kgs "kubectl get svc"
   Set-Alias kgd "kubectl get deployments"
   Set-Alias kgn "kubectl get nodes"
   Set-Alias kgcm "kubectl get configmap"
   Set-Alias kgsec "kubectl get secret"
   Set-Alias kgall "kubectl get all"
   Set-Alias kctx "kubectl config current-context"
   Set-Alias kdp "kubectl describe pod"
   Set-Alias kl "kubectl logs"
   Set-Alias klf "kubectl logs -f"
   ```

4. **Guarda el archivo y reinicia PowerShell o recarga el perfil:**
   ```powershell
   . $PROFILE
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
