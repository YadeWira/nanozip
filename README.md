## README Uso de NanoZip

NanoZip es una herramienta de compresión de archivos de alto rendimiento, diseñada para ofrecer una compresión eficiente y rápida. Es especialmente útil para manejar grandes volúmenes de datos y aprovechar al máximo los recursos del sistema, como múltiples núcleos de CPU y memoria.

A continuación, se detallan los comandos, opciones y ejemplos prácticos para utilizar NanoZip de manera efectiva.

---

### Instalación y Requisitos

NanoZip es compatible con sistemas **Linux64/32 y Windowsx64/86**. Para utilizarlo, simplemente descarga el ejecutable desde el sitio web no-oficial y asegúrate de que tenga permisos de ejecución:

```bash
chmod +x nz
```

---

### Comandos Principales

NanoZip ofrece varios comandos para realizar diferentes operaciones. Aquí están los más importantes:

1. **Añadir archivos a un archivo comprimido (`a`):**
   
   ```bash
   nz a <archivo_comprimido> <archivo1> <archivo2> ...
   ```
   
   - Este comando comprime uno o más archivos y los guarda en un archivo `.nz`.
   - Ejemplo:
     
     ```bash
     nz a backup.nz document1.txt document2.txt
     ```

2. **Comprimir una carpeta completa (`-r`):**
   
   ```bash
   nz a -r <archivo_comprimido> <carpeta>
   ```
   
   - La opción `-r` permite comprimir recursivamente todos los archivos dentro de una carpeta, incluyendo subcarpetas.
   - Ejemplo:
     
     ```bash
     nz a -r test.nz carpeta
     ```
     
     Esto comprimirá todo el contenido de la carpeta `carpeta` en el archivo `test.nz`.

3. **Listar el contenido de un archivo comprimido (`l`):**
   
   ```bash
   nz l <archivo_comprimido>
   ```
   
   - Muestra una lista de los archivos contenidos en el archivo comprimido.
   - Ejemplo:
     
     ```bash
     nz l test.nz
     ```

4. **Probar la integridad de un archivo comprimido (`t`):**
   
   ```bash
   nz t <archivo_comprimido>
   ```
   
   - Verifica que los archivos comprimidos no estén corruptos.
   - Ejemplo:
     
     ```bash
     nz t test.nz
     ```

5. **Extraer archivos de un archivo comprimido (`x`):**
   
   ```bash
   nz x <archivo_comprimido>
   ```
   
   - Extrae todos los archivos del archivo comprimido en el directorio actual.
   - Ejemplo:
     
     ```bash
     nz x test.nz
     ```

6. **Crear un archivo autoextraíble para Windows 32-bit (`w32c`):**
   
   ```bash
   nz w32c <archivo_comprimido>
   ```
   
   - Genera un archivo `.exe` que puede ser ejecutado en sistemas Windows para extraer los archivos sin necesidad de NanoZip.
   - Ejemplo:
     
     ```bash
     nz w32c backup.nz
     ```

7. **Mostrar información del sistema (`info`):**
   
   ```bash
   nz info
   ```
   
   - Muestra detalles sobre el sistema, como la CPU y la memoria disponible.

8. **Mostrar opciones avanzadas (`help`):**
   
   ```bash
   nz help
   ```
   
   - Proporciona una lista detallada de todas las opciones disponibles.

---

### Opciones de Compresión

NanoZip ofrece varias opciones para personalizar la compresión según tus necesidades:

1. **Seleccionar el compresor (`-c`):**
   
   - `-c<n,f,F,d,dp,dP,D,Dp,DP,o,O,c>`
   - Ejemplos:
     - `-cO` para usar el compresor `nz_optimum2` (recomendado para un equilibrio entre velocidad y compresión).
     - `-cd` para usar `nz_lzhd`.
     - `-cD` para usar `nz_lzhds_parallel`.

2. **Número de compresores en paralelo (`-p`):**
   
   - `-p<0...n>`
   - Ejemplo:
     - `-p4` para usar 4 compresores en paralelo (ideal para sistemas con múltiples núcleos).

3. **Limitar el uso de memoria (`-m`):**
   
   - `-m<0...n>[k,m,g]`
   - Ejemplo:
     - `-m1.2g` para limitar el uso de memoria a 1.2 GB.

4. **Ordenar archivos antes de comprimir (`-s`):**
   
   - `-s<n,e,a,s>`
   - Ejemplo:
     - `-se` para ordenar los archivos por extensión antes de comprimirlos.

---

### Opciones Generales

1. **Recursión en subdirectorios (`-r`):**
   
   - Permite comprimir todos los archivos dentro de una carpeta y sus subcarpetas.
   - Ejemplo:
     
     ```bash
     nz a -r backup.nz carpeta
     ```

2. **Número de hilos (`-t`):**
   
   - `-t<0...n>`
   - Ejemplo:
     - `-t8` para usar 8 hilos (ideal para CPUs con múltiples núcleos).

3. **Excluir archivos (`-x`):**
   
   - `-x<archivo>`
   - Ejemplo:
     - `-x*.log` para excluir todos los archivos con extensión `.log`.

4. **No almacenar timestamps (`-nt`):**
   
   - Omite la información de fecha y hora de los archivos comprimidos.

5. **No almacenar permisos (`-np`):**
   
   - Omite la información de permisos de los archivos comprimidos.

6. **No almacenar metadatos (`-nm`):**
   
   - Equivale a `-nt -np -hn` (no almacena timestamps, permisos ni checksum).

7. **Modo silencioso (`-y`):**
   
   - Responde "sí" a todas las preguntas automáticamente.

8. **Modo verbose (`-v`):**
   
   - Muestra información detallada durante la compresión.

---

### Ejemplos Prácticos

1. **Comprimir una carpeta con compresión óptima y 4 hilos:**
   
   ```bash
   nz a -r -cO -p4 -m1g backup.nz carpeta
   ```

2. **Extraer un archivo comprimido en un directorio específico:**
   
   ```bash
   nz x -o/ruta/de/destino backup.nz
   ```

3. **Crear un archivo autoextraíble para Windows:**
   
   ```bash
   nz w32c backup.nz
   ```

4. **Comprimir archivos excluyendo logs:**
   
   ```bash
   nz a -x*.log backup.nz carpeta
   ```

---

### Mensaje a Sami Runsas

Querido Sami Runsas,

Aunque ya no estás con nosotros, tu legado perdura a través de herramientas como NanoZip, que continúan siendo utilizadas y apreciadas por muchos en la comunidad de compresión de datos. Tu dedicación y talento han dejado una marca indeleble en el mundo de la tecnología, y tu trabajo sigue siendo una fuente de inspiración para aquellos que buscan innovar y mejorar en este campo.

Descansa en paz, Sami. Tu contribución al mundo no será olvidada.

Con respeto y admiración,  
Wira  

---

## Redes Sociales

Mis redes sociales:

- **GitHub**: [https://github.com/YadeWira](https://github.com/YadeWira)
- **SoundCloud**: [https://soundcloud.com/sy-wira](https://soundcloud.com/sy-wira)
- **YouTube**: [https://www.youtube.com/@LinuxPana](https://www.youtube.com/@LinuxPana)


