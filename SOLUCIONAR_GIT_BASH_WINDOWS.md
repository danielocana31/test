# Solucionar error de git-bash en Claude Code para Windows

## El error que tienes

```
Error: Claude Code on Windows requires git-bash (https://git-scm.com/downloads/win).
If installed but not in PATH, set environment variable pointing to your bash.exe,
similar to: CLAUDE_CODE_GIT_BASH_PATH=C:\Program Files\Git\bin\bash.exe
```

## ¿Por qué ocurre?

Claude Code en Windows necesita git-bash para ejecutar comandos de Linux/Unix. Aunque ya tengas Git instalado, Claude Code no lo encuentra porque:
- Git-bash no está en el PATH de Windows
- Claude Code no sabe dónde está instalado bash.exe

## Solución 1: Agregar git-bash al PATH (Recomendado)

### Paso 1: Encuentra dónde está bash.exe

Ubicaciones comunes:
```
C:\Program Files\Git\bin\bash.exe
C:\Program Files (x86)\Git\bin\bash.exe
C:\Users\TuUsuario\AppData\Local\Programs\Git\bin\bash.exe
```

Para verificar, abre el Explorador de Windows y busca en esas rutas.

### Paso 2: Agrega Git al PATH

1. **Abre Configuración del Sistema**:
   - Presiona `Windows + R`
   - Escribe: `sysdm.cpl`
   - Presiona Enter

2. **Ve a Variables de entorno**:
   - Haz clic en la pestaña "Opciones avanzadas"
   - Haz clic en "Variables de entorno..."

3. **Edita la variable PATH**:
   - En "Variables del sistema", busca `Path`
   - Haz clic en "Editar..."
   - Haz clic en "Nuevo"
   - Agrega: `C:\Program Files\Git\bin` (o donde esté tu Git)
   - Haz clic en "Aceptar" en todas las ventanas

4. **Reinicia VS Code y la terminal**
   - Cierra completamente VS Code
   - Abre VS Code de nuevo
   - Intenta usar Claude Code

### Paso 3: Verifica que funcione

Abre una nueva terminal (PowerShell o CMD) y ejecuta:
```bash
bash --version
```

Si ves la versión de bash, ¡funciona!

## Solución 2: Variable de entorno CLAUDE_CODE_GIT_BASH_PATH

Si no quieres modificar el PATH, puedes crear una variable específica para Claude Code.

### Opción A: Variable permanente

1. **Abre Variables de entorno** (como en Solución 1)

2. **Crea nueva variable**:
   - En "Variables del sistema", haz clic en "Nueva..."
   - Nombre: `CLAUDE_CODE_GIT_BASH_PATH`
   - Valor: `C:\Program Files\Git\bin\bash.exe` (tu ruta exacta)
   - Haz clic en "Aceptar"

3. **Reinicia VS Code**

### Opción B: Variable temporal (solo para la sesión actual)

En PowerShell:
```powershell
$env:CLAUDE_CODE_GIT_BASH_PATH = "C:\Program Files\Git\bin\bash.exe"
```

En CMD:
```cmd
set CLAUDE_CODE_GIT_BASH_PATH=C:\Program Files\Git\bin\bash.exe
```

Luego inicia VS Code desde esa misma terminal:
```bash
code .
```

## Solución 3: Reinstalar Git con configuración correcta

Si nada funciona, reinstala Git:

1. **Descarga Git**: https://git-scm.com/downloads/win

2. **Durante la instalación**:
   - ✅ Marca "Git from the command line and also from 3rd-party software"
   - ✅ Marca "Use Git and optional Unix tools from the Command Prompt"

3. **Completa la instalación y reinicia tu computadora**

## Verificar que Git Bash esté instalado correctamente

### Método 1: Buscar en el menú de inicio
- Busca "Git Bash" en el menú de inicio
- Si aparece, Git está instalado

### Método 2: Verificar archivos
Verifica que existan estos archivos:
```
C:\Program Files\Git\bin\bash.exe
C:\Program Files\Git\bin\sh.exe
C:\Program Files\Git\git-bash.exe
```

## Problemas comunes

### "bash.exe no está en esa ubicación"

Busca bash.exe en tu sistema:
1. Abre el Explorador de Windows
2. En la barra de búsqueda: `bash.exe`
3. Espera a que aparezcan resultados
4. Copia la ruta completa donde está

### "Sigo teniendo el error después de agregarlo al PATH"

1. Reinicia tu computadora (no solo VS Code)
2. Verifica que la ruta en PATH no tenga espacios extras
3. Asegúrate de que la ruta termine en `\bin`, no en `\bin\bash.exe`

### "Mi Git está en C:\Users\..."

Está bien, usa esa ruta. Por ejemplo:
```
C:\Users\Daniel\AppData\Local\Programs\Git\bin
```

## Configuración recomendada final

Después de solucionar:

1. **Verifica que funciona**:
   ```bash
   # En cualquier terminal
   bash --version
   git --version
   ```

2. **Prueba Claude Code**:
   - Abre VS Code
   - Inicia Claude Code
   - Intenta ejecutar un comando simple

## Comando de prueba en Claude Code

Una vez solucionado, prueba con:
```bash
echo "Hola desde bash"
```

Si Claude Code ejecuta esto sin errores, ¡está funcionando!

## Alternativa: Usar WSL (Windows Subsystem for Linux)

Si tienes muchos problemas, considera usar WSL:

1. **Instala WSL**:
   ```powershell
   wsl --install
   ```

2. **Reinicia tu PC**

3. **Trabaja desde WSL**:
   - Claude Code funciona mejor en entornos Unix
   - VS Code se integra perfectamente con WSL
   - No necesitas git-bash

Para más info: https://learn.microsoft.com/es-es/windows/wsl/install

## Resumen rápido

**Solución más rápida**:
1. Encuentra `bash.exe` (probablemente en `C:\Program Files\Git\bin\bash.exe`)
2. Crea variable: `CLAUDE_CODE_GIT_BASH_PATH` con esa ruta
3. Reinicia VS Code
4. ¡Listo!

**Solución más limpia**:
1. Agrega `C:\Program Files\Git\bin` al PATH
2. Reinicia la PC
3. Todo funcionará automáticamente
