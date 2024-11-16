# Generador de Cotizaciones para el Ministerio de la Producción - Perú

https://generarcotizacion.streamlit.app/

## Descripción

Esta aplicación permite generar una cotización y los documentos requeridos para el proceso de contratación de servicios, cumpliendo con los lineamientos del Ministerio de la Producción del Perú. Utiliza tecnología avanzada para extraer datos de los documentos proporcionados y permite al usuario introducir datos personales, incluyendo la selección precisa de ubicación en un mapa interactivo, que facilita la correcta identificación de la dirección.

Se incorporó una funcionalidad avanzada que permite a los usuarios eliminar el fondo de sus firmas de manera sencilla y efectiva. Utilizando la biblioteca Rembg, que se basa en técnicas de segmentación de imágenes, permite obtener firmas limpias y profesionales. Esta herramienta está estrechamente relacionada con OpenCV, una de las bibliotecas más reconocidas en el ámbito del procesamiento de imágenes. Al integrar Rembg, garantizamos que las firmas se presenten sin distracciones, mejorando así la calidad visual de los documentos generados. Con esta funcionalidad, los usuarios pueden cargar sus firmas y disfrutar de resultados de alta calidad, donde el fondo no deseado es eliminado automáticamente, permitiendo que la firma resalte en el contexto de la cotización.

## Características

- **Extracción de Datos**: La aplicación analiza el **Término de Referencia (TDR)** para identificar detalles como el nombre del servicio, el plazo de entrega y la forma de pago.
- **Integración con APIs**: Conecta con la API de SUNAT para obtener información actualizada a partir del DNI ingresado.
- **Selección de Ubicación en Mapa Interactivo**: Permite a los usuarios seleccionar su ubicación exacta en un mapa utilizando el servicio de geolocalización y la biblioteca de mapas **Folium**. Esta funcionalidad no solo facilita la obtención de la dirección del usuario, sino que también ofrece la opción de actualizarla manualmente a través del mapa en la interfaz de usuario.
- **Generación de Documentos Automática**: A partir de una plantilla (`FormatoCotizacion.docx`), la aplicación genera el documento de cotización con los datos ingresados y procesados.
- **Generación de ZIP**: Los documentos generados y el TDR original se agrupan en un archivo ZIP descargable para facilidad del usuario.
- **Interfaz de Usuario Intuitiva**: Desarrollada con Streamlit, la aplicación ofrece una experiencia fluida para usuarios de todos los niveles.

## Requisitos

- Python 3.7 o superior
- [Streamlit](https://streamlit.io/)
- `requests`
- `Pillow`
- `geopy`
- `pdfplumber`
- `python-docx`
- `folium`
- `streamlit_folium`
- `streamlit_js_eval`
- `streamlit_image_comparison`
- `rembg`

## Instalación

1. Clona el repositorio:
   ```bash
   git clone https://github.com/jersonalvr/cotizacion/
   cd cotizacion
   ```

2. Instala las dependencias:
   ```bash
   pip install -r requirements.txt
   ```

3. Configura las credenciales de SUNAT:
   - Coloca tu clave API de SUNAT en el archivo de configuración `secrets.toml` en la carpeta `.streamlit`, de la siguiente manera:
     ```toml
     [APISNET]
     key = "TU_CLAVE_API"
     ```

4. Agrega la plantilla de Word (`FormatoCotizacion.docx`) y la imagen de Yape (`yape.png`) en el directorio base de la aplicación.

## Uso

1. Ejecuta la aplicación:
   ```bash
   streamlit run app.py
   ```

2. En la interfaz de Streamlit:
   - Sube el **TDR** en formato PDF.
   - Ingresa tu **DNI** para obtener información de SUNAT.
   - Ingresa los datos personales y de contacto.
   - **Ubicación en el Mapa**: Utiliza el botón de geolocalización para obtener tu ubicación actual o selecciona un punto manualmente en el mapa para actualizar tu dirección. La aplicación obtendrá automáticamente la dirección completa basada en las coordenadas.
   - Proporciona la información bancaria, incluyendo el banco y el número de cuenta.
   - Define el monto de la oferta y confirma para generar los documentos.

3. **Descarga el archivo ZIP** generado, que incluirá:
   - Documento de cotización.
   - Archivos requeridos para el proceso de contratación.

## Créditos

Esta aplicación fue desarrollada para optimizar la generación de cotizaciones y documentos administrativos en el proceso de contratación de servicios para el **Ministerio de la Producción del Perú**.

## Licencia

[MIT](LICENSE)

---

La URL del repositorio se ha actualizado a `https://github.com/jersonalvr/cotizacion/`.
