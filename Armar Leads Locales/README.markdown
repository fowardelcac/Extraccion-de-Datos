# Scraper de Números Telefónicos desde Google Maps

## Descripción

Este script en Python extrae números telefónicos de páginas web a partir de una lista de URLs almacenada en un archivo Excel. Utiliza `pandas` para manejar los datos, `selenium` para la navegación web, `BeautifulSoup` para el análisis HTML y expresiones regulares para validar números telefónicos.

## Requisitos

- Python 3.x instalado.
- Librerías necesarias:
  - `pandas`
  - `selenium`
  - `beautifulsoup4`
  - `re` (incluido en Python)
- Google Chrome instalado.
- ChromeDriver compatible con la versión de Chrome instalada.

## Instalación

1. Instala las librerías necesarias ejecutando:

   ```bash
   pip install pandas selenium beautifulsoup4
   ```

2. Descarga e instala ChromeDriver desde aquí y asegúrate de que esté en el PATH del sistema.

## Uso

1. Coloca el archivo Excel con las URLs en la ruta especificada (por ejemplo, `C:/Users/juans/Documents/cv/Proyectos/Extraccion de Datos/Armar Leads Locales/Posibles Clientes.xlsx`).
2. Asegúrate de que el archivo tenga una columna llamada `Url` con las URLs y una columna `Unnamed: 2` para almacenar los números telefónicos.
3. Ejecuta el script:

   ```bash
   python script.py
   ```

## Funcionamiento

1. **Carga del Excel**: Lee el archivo Excel y filtra las filas donde la columna `Unnamed: 2` está vacía.
2. **Expresión regular**: Define un patrón para identificar números telefónicos con formatos como `+123 456 7890` o `123-456-7890`.
3. **Filtrado de números**:
   - La función `filter_number` busca y valida números telefónicos en los elementos extraídos de la página.
4. **Scraping**:
   - La función `scrapper` recorre las URLs del DataFrame.
   - Usa Selenium para cargar cada página y BeautifulSoup para analizar el HTML.
   - Busca elementos `<div>` con la clase `Io6YTe` y extrae números telefónicos válidos.
   - Actualiza la columna `Unnamed: 2` con el número encontrado o `None` si no hay coincidencias.
5. **Guardado**: Une los resultados con el DataFrame original y guarda el resultado en un nuevo archivo Excel (`Cba_final.xlsx`).
