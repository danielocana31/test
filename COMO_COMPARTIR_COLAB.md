# Cómo compartir tu trabajo de Google Colab con Claude

Hay varias formas de compartir lo que haces en Google Colab para que pueda ayudarte:

## Opción 1: Copiar y pegar código (Más rápido)

1. En tu notebook de Colab, selecciona el código de la celda que quieres compartir
2. Copia el código (Ctrl+C o Cmd+C)
3. Pégalo directamente en el chat conmigo

**Ejemplo:**
```
Tengo este código en Colab que no funciona:

import pandas as pd
df = pd.read_csv('data.csv')
print(df.head())
```

## Opción 2: Compartir enlace público de Colab

1. En tu notebook de Colab, haz clic en "Compartir" (arriba a la derecha)
2. Cambia el acceso a "Cualquier persona con el enlace"
3. Copia el enlace
4. Comparte el enlace conmigo

**Nota:** Puedo leer notebooks de Colab públicos usando herramientas de web, pero es más lento que copiar el código directamente.

## Opción 3: Descargar y compartir el notebook (.ipynb)

1. En Colab: Archivo → Descargar → Descargar .ipynb
2. Guarda el archivo en tu repositorio Git
3. Haz commit y push
4. Puedo leer el archivo directamente del repositorio

## Opción 4: Capturas de pantalla

Para errores o visualizaciones:
1. Toma una captura de pantalla
2. Comparte la imagen conmigo
3. Puedo ver y analizar el contenido visual

## ¿Qué opción usar?

- **Para código corto o errores específicos**: Opción 1 (copiar y pegar)
- **Para notebooks completos**: Opción 2 (enlace) u Opción 3 (.ipynb)
- **Para errores visuales o gráficos**: Opción 4 (capturas)

## Ejemplo de uso

**Tú dices:**
```
Tengo este error en Colab:

[código o captura del error]

¿Cómo lo soluciono?
```

**Yo puedo:**
- Analizar el código
- Explicar el error
- Sugerir soluciones
- Escribir código corregido

## Limitaciones

Como Claude Code, puedo:
- ✅ Leer y analizar código de Colab
- ✅ Explicar errores y sugerir soluciones
- ✅ Escribir código que puedes copiar a Colab
- ❌ NO puedo ejecutar código directamente en tu Colab
- ❌ NO puedo acceder a tu cuenta de Google Colab
- ❌ NO puedo ver notebooks privados sin que los compartas

**¿Por qué estas limitaciones?** Lee la [explicación técnica completa](POR_QUE_NO_COLAB_DIRECTO.md) que incluye alternativas y qué se necesitaría para hacerlo posible.

## Preguntas frecuentes

**P: ¿Puedes ejecutar código en mi Colab?**
R: No, pero puedo escribir código que tú ejecutes allí.

**P: ¿Puedes ver mi Colab sin compartirlo?**
R: No, necesitas compartir el enlace público o copiar el código.

**P: ¿Es seguro compartir mi enlace de Colab?**
R: Solo hazlo si no contiene datos sensibles. Puedes hacer el enlace privado después.
