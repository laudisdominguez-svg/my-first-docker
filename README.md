# my-first-docker
Documentation of my first steps with Docker, including installation guide and learning tutorial.
# Mi Primer Docker en Windows con WSL 🐳

> Una guía educativa paso a paso para tu **primer contenedor Docker en Windows** usando WSL

Este es mi primer proyecto con Docker: documentando todo el proceso de instalación, configuración y la satisfacción de ver un contenedor funcionando en tu navegador local.

## 🎯 ¿Qué es esto?

- ✅ **Guía práctica** para instalar Docker en Windows
- ✅ **Tutorial paso a paso** para principiantes
- ✅ **Mi primer contenedor** (Nginx) funcionando
- ✅ **Solución de problemas comunes**

**No es** un proyecto de código, sino **documentación de aprendizaje**.

## 📋 Requisitos

- Windows 10 o 11
- PowerShell con permisos de administrador
- Conexión a internet
- ~5-10 minutos de tiempo

## 📁 Estructura del Repositorio

```
mi-primer-docker/
└── README.md    ← Todo lo que necesitas
```

Ese es todo el proyecto. Solo documentación. Simple y directo.

## 🚀 Instalación Rápida

### 1. Verifica e Instala WSL

```powershell
# Ver distribuciones disponibles
wsl --list --online

# Instalar Ubuntu
wsl --install -d Ubuntu

# Ver distribuciones instaladas
wsl --list --verbose
```

### 2. Entra a Ubuntu

```powershell
wsl -d Ubuntu
```

Deberías ver:
```
usuario@PC:~$
```

### 3. Instala Docker

```bash
# Actualiza paquetes
sudo apt-get update

# Instala Docker
sudo apt-get install docker.io -y

# Verifica instalación
docker --version
```

### 4. Habilita e Inicia Docker

```bash
# Habilita para iniciar automáticamente
sudo systemctl enable docker

# Inicia el servicio
sudo systemctl start docker
```

### 5. Resuelve Permisos (Si necesario)

Si ves `PERMISSION DENIED`:

```bash
# Agrega tu usuario al grupo docker
sudo usermod -aG docker tu_usuario

# Opción 1: Cierra y reabre Ubuntu
exit
# Desde PowerShell
wsl -d Ubuntu

# Opción 2: Activa ahora
newgrp docker

# Verifica que funciona
docker ps
```

## ✅ Tu Primer Contenedor

```bash
# Ejecuta Nginx
docker run -d -p 8080:80 nginx

# Verifica que corre
docker ps
```

**Abre tu navegador:** `http://localhost:8080`

Deberías ver la página de bienvenida de Nginx ✨

## 📚 Comandos Útiles

```bash
# Ver todos los contenedores (incluso detenidos)
docker ps -a

# Detener un contenedor
docker stop CONTAINER_ID

# Eliminar un contenedor
docker rm CONTAINER_ID

# Ver logs
docker logs CONTAINER_ID

# Eliminar una imagen
docker rmi IMAGE_ID
```

## 🔧 Solución de Problemas

### "docker: command not found"
→ Docker no está instalado o no estás en Ubuntu vía WSL

### "Permission denied while trying to connect to Docker"
→ Tu usuario no está en el grupo docker (sigue paso 5)

### "Port 8080 already in use"
→ Usa otro puerto: `docker run -d -p 8081:80 nginx`

### "Cannot connect to Docker daemon"
→ Inicia el servicio: `sudo systemctl start docker`

## 📖 ¿Qué Aprendiste?

- ✅ WSL permite ejecutar Linux en Windows
- ✅ Docker requiere permisos especiales en Linux
- ✅ Un contenedor es una aplicación empacada y aislada
- ✅ Puedes mapear puertos para acceder desde Windows
- ✅ Docker Hub tiene miles de imágenes listas para usar

## 📖 ¿Qué Aprendiste?

Después de seguir esta guía, entiendes:

- ✅ **WSL** permite ejecutar Linux en Windows
- ✅ **Docker** empaca aplicaciones en contenedores aislados
- ✅ **Los permisos** son importantes en Linux (solución de problemas)
- ✅ **Mapeo de puertos** conecta tu máquina con el contenedor
- ✅ **Docker Hub** tiene miles de imágenes listas para usar
- ✅ Cómo **verificar** que todo funciona correctamente

## 🎓 Lecciones Clave

1. **La documentación es tu aliada** - Cada paso debe verificarse
2. **Los errores enseñan** - "Permission denied" es normal, no es un fallo tuyo
3. **Docker simplifica las cosas** - Una línea de comando = un servidor funcionando
4. **El aprendizaje es celebrar** - Ver Nginx en tu navegador es motivo de alegría 🎉

## 🔗 Referencias

- [Documentación oficial de Docker](https://docs.docker.com)
- [Documentación de WSL](https://learn.microsoft.com/en-us/windows/wsl/)
- [Docker Hub - Imágenes oficiales](https://hub.docker.com)
- [Nginx en Docker](https://hub.docker.com/_/nginx)

## 📝 Notas

- Este proyecto es **educativo y de aprendizaje**
- Perfecto para **principiantes en Windows**
- Probado en **Windows 11 + Ubuntu 22.04**
- Si encuentras problemas, consulta la sección de troubleshooting

## 🌟 Siguientes Pasos

Una vez domines esto:

1. **Crea un Dockerfile personalizado** para tu aplicación
2. **Explora Docker Compose** para múltiples contenedores
3. **Publica en Docker Hub** tus propias imágenes
4. **Comparte tu conocimiento** con otros principiantes

## 📄 Licencia

Contenido educativo libre de usar y compartir. Haz que otros también aprendan Docker.

---

**¿Te funcionó?** Si esta guía te ayudó, ¡déjame una ⭐ en GitHub!

**¿Tienes preguntas?** Abre un issue o comenta en DEV.to.

**¿Lograste tu primer contenedor?** ¡Felicidades! Acabas de entrar al mundo de Docker 🐳🎉
