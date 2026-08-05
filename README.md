# 🛡️ AUR Auditor (Bash Script)

Un script en Bash ligero e interactivo para auditar la seguridad de los paquetes del **Arch User Repository (AUR)** antes de compilarlos o instalarlos. 

Diseñado para detectar de forma rápida posibles ataques en la cadena de suministro (*Supply Chain Attacks*) o comportamientos sospechosos en scripts de instalación, mediante la inspección en tiempo real de los archivos `PKGBUILD`.

---

## 🚀 Características

* **Detección automática de Helper:** Detecta si tu sistema utiliza `paru` o `yay`.
  
* **Búsqueda eficiente:** Utiliza la API del helper (`-Ssq`) para listar coincidencias de paquetes al instante.
  
* **Menú interactivo:** Permite elegir el paquete deseado mediante una lista numerada nativa en Bash.
  
* **Inspección sin descargas pesadas:** Extrae e inspecciona únicamente el contenido del `PKGBUILD` en memoria, sin clonar repositorios ni descargar código fuente al disco.
  
* **Análisis estático de código:** Escanea el archivo buscando palabras clave y comandos potencialmente peligrosos o inusuales mediante expresiones regulares con límites de palabra (`grep -iEw`).
  
* **Visor integrado:** Opción para desplegar el `PKGBUILD` completo directamente en la terminal.

---

## 🔍 Textos y Comandos Auditados

El script alerta si detecta el uso de:

* **Gestores de paquetes externos:** `npm`, `bun`, `npx`, `pip`, `pip3`, `gem`, `cargo` (usados frecuentemente para inyectar dependencias de terceros fuera del control de `pacman`).
  
* **Descargadores y ejecutores:** `curl`, `wget`, `fetch`, `base64`, `eval`, `exec`.
  
* **Tuberías de ejecución remota (Red Flags):** Comandos estilo `curl | bash` o `wget | sh`.

---

## 📋 Requisitos Previos

* **Arch Linux** (o distribuciones derivadas como EndeavourOS, CachyOS, etc.).
  
* Al menos uno de los siguientes *AUR Helpers*:
  * `paru`
  * `yay`

* Bash 4.0 o superior.

---

## 🛠️ Instalación y Uso

1. **Clona este repositorio o descarga el script:**
   ```bash
   git clone [https://github.com/tu-usuario/aur-auditor.git](https://github.com/srdazagit/AUR-check.git)
   cd AUR-check
   
