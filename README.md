# test

## Documentación y Guías

### Google Colab
- **[Cómo compartir tu trabajo de Google Colab](COMO_COMPARTIR_COLAB.md)** - Guía completa de integración
- **[¿Por qué no puede ejecutarse directamente en Colab?](POR_QUE_NO_COLAB_DIRECTO.md)** - Limitaciones técnicas y alternativas

### Configuración en Windows
- **[Solucionar error de git-bash en Windows](SOLUCIONAR_GIT_BASH_WINDOWS.md)** - Guía paso a paso

### Problemas en Ubuntu/Linux
- **[Solucionar error de apt/dpkg lock](SOLUCIONAR_APT_DPKG_UBUNTU.md)** - Errores de dpkg e instalación de Node.js

---

## Inicio rápido

### Usar con Google Colab

La forma más fácil de compartir tu código de Colab:
1. **Copia el código** de tu celda de Colab
2. **Pégalo** en el chat con Claude Code
3. Describe qué necesitas ayuda

### Configurar en Windows

Si ves error de git-bash:
1. Crea variable de entorno: `CLAUDE_CODE_GIT_BASH_PATH`
2. Valor: `C:\Program Files\Git\bin\bash.exe` (tu ruta de Git)
3. Reinicia VS Code

Ver [guía detallada](SOLUCIONAR_GIT_BASH_WINDOWS.md) para más opciones.

### Solucionar error de apt en Ubuntu

**Error de dpkg lock:**
Si ves "unable to acquire the dpkg frontend lock":

```bash
# 1. Verificar si hay procesos de apt corriendo
ps aux | grep -i apt

# 2. Esperar 5 minutos si los hay, o eliminar locks:
sudo rm /var/lib/dpkg/lock-frontend
sudo dpkg --configure -a

# 3. Instalar Node.js correctamente
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs
```

**Error de systemd/passwd lock:**
Si ves "Failed to take /etc/passwd lock" o error con systemd:

```bash
# Solución más fácil: Usa nvm (evita todos los problemas de apt)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
source ~/.bashrc
nvm install --lts
node --version
```

Ver [guía completa](SOLUCIONAR_APT_DPKG_UBUNTU.md) para más soluciones y diagnóstico.