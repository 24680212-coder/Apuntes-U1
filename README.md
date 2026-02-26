# 📚 Unidad I: Introducción a la Graficación por Computadora

Este apartado comprende el marco teórico y práctico fundamental para el estudio de los gráficos computacionales, desde sus orígenes históricos hasta las técnicas modernas de procesamiento de imágenes.

---

## 1.1 Historia y Evolución de la Graficación por Computadora
La graficación ha evolucionado de representaciones visuales rudimentarias a simulaciones fotorrealistas complejas:

* **Primeros hitos (1950-1960):** El inicio se marca con el proyecto **Whirlwind** y el sistema de defensa **SAGE**, que utilizaban pantallas para mostrar datos vectoriales. En 1963, Ivan Sutherland revolucionó el área con **Sketchpad**, introduciendo la interactividad y las estructuras de datos jerárquicas para gráficos.
* **Fundamentos del realismo (1970-1980):** Se desarrollaron algoritmos críticos de visibilidad y sombreado, como el sombreado de **Gouraud** y **Phong**. Aparecieron las técnicas de mapeo de texturas y el concepto de **Z-Buffer** para la gestión de profundidad.
* **Aceleración por Hardware (1990-Actualidad):** La creación de la GPU (Unidad de Procesamiento Gráfico) permitió delegar la carga matemática de la CPU al hardware especializado. Hoy en día, el enfoque está en el **Ray Tracing** en tiempo real y la reconstrucción de imágenes mediante Inteligencia Artificial.

## 1.2 Áreas de Aplicación
La graficación por computadora es un campo multidisciplinario con aplicaciones en:
* **Diseño Asistido por Computadora (CAD/CAM):** Vital en ingeniería y arquitectura para el diseño de prototipos y estructuras.
* **Entretenimiento:** Desarrollo de videojuegos, efectos visuales (VFX) para cine y simuladores de realidad virtual.
* **Ciencia y Medicina:** Visualización de fenómenos físicos, diagnósticos mediante tomografías 3D y simulaciones moleculares.
* **Sistemas de Información Geográfica (SIG):** Representación de datos topográficos y mapas dinámicos.
* **Interfaces Gráficas de Usuario (GUI):** El diseño visual que permite la interacción humana con el software.

## 1.3 Aspectos Matemáticos de la Graficación
Los gráficos digitales son proyecciones de modelos matemáticos:
* **Álgebra Lineal:** El uso de vectores para definir puntos y direcciones, y matrices para realizar transformaciones (Traslación, Rotación y Escalado).
* **Coordenadas Homogéneas:** Un sistema que permite unificar todas las transformaciones geométricas en multiplicaciones de matrices de 4x4, facilitando el procesamiento en hardware.
* **Geometría Analítica:** Utilizada para el cálculo de intersecciones, normales de superficie y la determinación de la visibilidad de las caras de un objeto.



## 1.4 Modelos del Color
El color se representa mediante modelos que cuantifican la luz y el pigmento:
* **RGB (Red, Green, Blue):** Modelo aditivo basado en la luz. Se utiliza en monitores y dispositivos digitales. La suma de los tres colores al 100% genera blanco.
* **CMY/CMYK (Cyan, Magenta, Yellow, Black):** Modelo sustractivo basado en pigmentos. Es el estándar para la impresión industrial.
* **HSV (Hue, Saturation, Value):** Modelo orientado a la percepción humana. Define el matiz (color), la pureza (saturación) y la intensidad de luz (valor).
* **HSL (Hue, Saturation, Lightness):** Similar al HSV, pero organiza los colores en un espacio que facilita el ajuste de la luminosidad.



---

### 💡 Tutorial: Iluminación de un Cubo y sus Caras en Blender
La iluminación es el proceso de simular cómo la luz interactúa con la geometría para crear volumen y profundidad:

1.  **Fuentes de Luz:** En Blender, se pueden utilizar luces de tipo *Point* (luz en todas direcciones), *Sun* (rayos paralelos), *Spot* (cono de luz) o *Area* (luz desde un plano).
2.  **Sombreado de Caras (Flat vs. Smooth):** El *Flat Shading* muestra cada cara con un color sólido según su ángulo respecto a la luz, ideal para estilos de baja poligonalización. El *Smooth Shading* interpola los valores entre caras para dar una apariencia curva.
3.  **Configuración de Materiales:** Mediante el nodo *Principled BSDF*, se ajustan propiedades como el *Specular* (reflejo de la luz) y el *Roughness* (aspereza de la superficie) para determinar cómo se ilumina cada cara del cubo.

---

## 1.5 Representación y Trazo de Líneas y Polígonos
La rasterización es el proceso de convertir figuras matemáticas en píxeles:
* **Algoritmo DDA:** Un método simple de trazo de líneas que calcula incrementos basados en la pendiente, aunque requiere operaciones de punto flotante.
* **Algoritmo de Bresenham:** El estándar de eficiencia; utiliza aritmética de enteros para determinar qué píxel encender, optimizando el rendimiento del procesador.

### 1.5.1 Formatos de Imagen
* **Imágenes Raster (Mapas de bits):** Compuestas por una rejilla de píxeles.
    * **JPEG:** Ideal para fotografías por su alta compresión, aunque con pérdida de datos.
    * **PNG:** Compresión sin pérdida y soporte para transparencia (Canal Alpha).
    * **GIF:** Soporta animaciones y una paleta limitada de 256 colores.
* **Imágenes Vectoriales:** Basadas en fórmulas matemáticas. No pierden calidad al ser escaladas.
    * **SVG:** El formato vectorial estándar para la web.

---


---

## 1.6 Procesamiento de Mapas de Bits
El procesamiento implica la manipulación directa de la matriz de píxeles:
* **Filtros de Convolución:** Aplicación de matrices (kernels) para realizar efectos como desenfoque, enfoque o detección de bordes.
* **Transformaciones de Color:** Ajuste de histogramas, brillo, contraste y conversión de imágenes a escala de grises o binarias (umbralización).
* **Histograma de imagen:** Representación gráfica de la distribución de intensidades de color en una imagen.

---
---

## 📚 Bibliografía y Fuentes de Consulta (Recursos Digitales)

Para la elaboración de estos apuntes se consultaron las siguientes fuentes disponibles en plataformas digitales, siguiendo el formato **APA (7ma Edición)**:

* **Blender Foundation. (2024).** *Blender 4.0 Reference Manual*. Recuperado de [https://docs.blender.org/manual/es/latest/](https://docs.blender.org/manual/es/latest/)
  *(Guía oficial digital para los apartados de iluminación y modelado 3D).*

* **Cisneros, M. P. (2018).** *Graficación por computadora*. [Archivo PDF]. Recuperado de [https://www.academia.edu/37525301/Graficacion_por_computadora](https://www.academia.edu/37525301/Graficacion_por_computadora)
  *(Libro digital académico que cubre la historia y algoritmos de trazo).*

* **Khronos Group. (2023).** *OpenGL de Referencia Rápida*. Recuperado de [https://www.khronos.org/opengl/](https://www.khronos.org/opengl/)
  *(Documentación técnica digital sobre el procesamiento de gráficos y rasterización).*

* **Pascual, R. (2021).** *Modelos de Color y Espacios de Color*. [Artículo web]. Recuperado de [https://proyectacolor.cl/teoria-del-color/modelos-de-color/](https://proyectacolor.cl/teoria-del-color/modelos-de-color/)
  *(Recurso digital detallado sobre la comparativa entre RGB, CMYK y HSV).*

* **University of Cambridge. (s.f.).** *Computer Graphics: Algorithms and Mathematics*. [Material de curso digital]. Recuperado de [https://www.cl.cam.ac.uk/teaching/current/CompGraph/](https://www.cl.cam.ac.uk/teaching/current/CompGraph/)
  *(Apuntes digitales de alto nivel sobre los aspectos matemáticos de la graficación).*

* **Wolfram MathWorld. (2024).** *Bresenham's Line Algorithm*. Recuperado de [https://mathworld.wolfram.com/BresenhamsLineAlgorithm.html](https://mathworld.wolfram.com/BresenhamsLineAlgorithm.html)
  *(Enciclopedia matemática digital para la validación de algoritmos de trazo).*

---

---
  
