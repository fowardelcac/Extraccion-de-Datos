# Descargador de Imágenes desde URLs

## Descripción

Este script en Python permite descargar imágenes desde una lista de URLs extraídas de un archivo CSV y guardarlas en una carpeta específica en el sistema local. Utiliza las librerías `pandas`, `selenium`, `requests` y `os` para automatizar el proceso de descarga.

## Requisitos

- Python 3.x instalado.
- Librerías necesarias:
  - `pandas`
  - `selenium`
  - `requests`
- Google Chrome instalado.
- ChromeDriver compatible con la versión de Chrome instalada.

## Instalación

1. Instala las librerías necesarias ejecutando:

   ```bash
   pip install requirements.txt
   ```

2. Descarga e instala ChromeDriver desde aquí y asegúrate de que esté en el PATH del sistema.

## Uso

1. Coloca el archivo CSV con las URLs en la ruta especificada en el script (por ejemplo, `C:/Users/juans/Documents/cv/Proyectos/Extraccion de Datos/Construccion Dataset Fotos/istockphoto.csv`).
2. Asegúrate de que la columna que contiene las URLs se llame `Link`.
3. Especifica la carpeta de destino para las imágenes descargadas en la variable `final_folder`.
4. Ejecuta el script:

   ```bash
   python script.py
   ```

## Funcionamiento

1. **Carga del CSV**: Lee el archivo CSV y extrae las URLs de la columna `Link`.
2. **Configuración del navegador**: Inicializa un navegador Chrome en modo sin interfaz gráfica (headless).
3. **Descarga de imágenes**:
   - Para cada URL, accede a la página web.
   - Busca el elemento de la imagen usando su nombre de etiqueta (`img`).
   - Extrae el atributo `src` que contiene la URL directa de la imagen.
   - Realiza una solicitud GET para descargar la imagen.
   - Guarda la imagen en la carpeta especificada con un nombre único basado en la URL.
4. **Manejo de errores**: Si falla la descarga de una imagen, imprime un mensaje de error con el código de estado.

## Notas

- istockphoto.csv fue obtenido con Instant Data Scraper, extension de chrome que realiza scrapings. Obtuve todos los links de cada imagen, para luego procesar individualmente cada uno, ahorrando pasos extras
