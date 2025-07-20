🛠️ Dev Aliases Cross-Platform

Este repositorio contiene configuraciones de alias personalizados para Git y K8S (Kubernetes), optimizadas para diferentes entornos y sistemas operativos. Cada plataforma tiene sus propios alias adaptados a las convenciones y herramientas específicas del sistema.

## 🎯 Propósito

Proporcionar un conjunto consistente y eficiente de alias de desarrollo que:
- Aceleren el flujo de trabajo con Git y herramientas de desarrollo como K8s
- Mantengan consistencia entre diferentes sistemas operativos
- Sean fáciles de instalar y personalizar
- Incluyan documentación específica para cada plataforma

## 📁 Estructura del Repositorio
git config --global --list
```
dev-aliases/
├── 💻 powershell/     # Configuración para Windows PowerShell
├── 🍎 mac/           # Configuración para macOS (Zsh)
├── 🐧 linux/         # Configuración para Linux (Bash)
└── 🧰 gitbash/       # Configuración para Git Bash
```

**Cada carpeta contiene:**
- Archivo de configuración específico del sistema
- README.md con instrucciones detalladas de instalación
- Documentación de los alias disponibles

## 📌 Alias Principales Incluidos

### Git Workflow
- **gst** → `git status` - Estado del repositorio
- **gpl** → `git pull` - Obtener cambios remotos
- **gcom** → `git commit -m` - Commit con mensaje

### Navegación y Utilidades
- Alias para navegación rápida de directorios
- Comandos de desarrollo comunes
- Herramientas de productividad específicas por plataforma

## 🚀 Instrucciones de Instalación

**⚠️ Importante:** Cada sistema operativo tiene sus propias instrucciones de instalación. Por favor, navega a la carpeta correspondiente a tu sistema:

- **💻 Windows:** [`powershell/README.md`](powershell/README.md)
- **🍎 macOS:** [`mac/README.md`](mac/README.md)  
- **🐧 Linux:** [`linux/README.md`](linux/README.md)
- **🧰 Git Bash:** [`gitbash/README.md`](gitbash/README.md)

Cada guía incluye:
- Pasos detallados de instalación
- Configuración específica del sistema
- Lista completa de alias disponibles
- Troubleshooting común
- Personalización avanzada

## 🔧 Personalización

Los archivos están diseñados para ser fácilmente personalizables. Puedes:
- Modificar alias existentes
- Agregar tus propios alias
- Adaptar la configuración a tu flujo de trabajo

## 🤝 Contribución

Si encuentras mejoras o tienes alias útiles para agregar, las contribuciones son bienvenidas. Asegúrate de mantener la consistencia entre plataformas cuando sea posible.