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
### 🛠️ Práctica: Dibujo de la Flor de la Vida 

En esta práctica se aplica el uso de ciclos `while` y funciones trigonométricas para generar un patrón geométrico complejo. El algoritmo se basa en la repetición de círculos cuyos centros se desplazan sobre el perímetro de un círculo central.

#### Explicación de las Funciones Utilizadas:
Para posicionar los círculos, el script utiliza las siguientes funciones del módulo `math`:
* **math.cos(angulo):** Calcula la posición en el eje X.
* **math.sin(angulo):** Calcula la posición en el eje Y.
* **math.radians(grados):** Convierte grados (0-360) a radianes, ya que Python usa radianes para los cálculos.
  
#### Código Fuente (Blender Python):

```python
import bpy
import math

# 1. Limpieza de la escena previa
bpy.ops.object.select_all(action="SELECT")
bpy.ops.object.delete()

# 2. Parámetros de la figura
radio = 3
segmentos = 64
paso_angular = 60  # Incremento para obtener 6 círculos exactos
angulo_actual = 0
contador = 0

# 3. Creación del círculo central
bpy.ops.mesh.primitive_circle_add(radius=radio, location=(0, 0, 0), vertices=segmentos)

# 4. Ciclo para la generación de la estructura periférica
while contador < 6:
    # Cálculo trigonométrico de la posición del nuevo centro
    x = radio * math.cos(math.radians(angulo_actual))
    y = radio * math.sin(math.radians(angulo_actual))
    
    # Generación del círculo en la posición calculada
    bpy.ops.mesh.primitive_circle_add(radius=radio, location=(x, y, 0), vertices=segmentos)
    
    # Actualización para la siguiente iteración
    angulo_actual += paso_angular  # Desplazamiento de 60 grados
    contador += 1                  # Incremento del control de ciclo
```
A continuación se muestra el código en ejecución:

<img width="1920" height="1008" alt="Captura de pantalla 2026-02-25 201813" src="https://github.com/user-attachments/assets/4bd87784-a8f7-477d-a3a8-443bdd739447" />

### 🛠️ Práctica: Dibujo de un Polígono Regular (Construcción de Mallas)

En esta práctica se profundiza en la creación de geometría personalizada. A diferencia de la práctica anterior, aquí no usamos una función de "crear círculo", sino que definimos manualmente los **vértices** (puntos en el espacio) y las **aristas** (líneas que conectan los puntos).

#### Conceptos Clave de la API de Blender:
1.  **bpy.data.meshes.new:** Crea la estructura de datos que contendrá la geometría.
2.  **bpy.data.objects.new:** Crea el contenedor (objeto) que permite que la malla exista en la escena 3D.
3.  **malla.from_pydata:** Es la función fundamental que recibe tres listas: Vértices, Aristas y Caras.
    * `Vértices`: Lista de coordenadas (x, y, z).
    * `Aristas`: Conexiones entre el índice de un vértice y otro.
    * `Caras`: Superficies cerradas (en este ejercicio se deja vacío `[]`).



#### Código Fuente (Blender Python):

```python
import bpy
import math

def crear_poligono_2d(nombre, lados, radio):
    # 1. Limpiar la escena antes de empezar
    bpy.ops.object.select_all(action='SELECT')
    bpy.ops.object.delete()

    # 2. Crear una nueva malla y un objeto
    malla = bpy.data.meshes.new(nombre)
    objeto = bpy.data.objects.new(nombre, malla)
    
    # 3. Vincular el objeto a la escena actual
    bpy.context.collection.objects.link(objeto)
    
    vertices = []
    aristas = []
    
    # 4. Cálculo matemático de vértices (Distribución circular)
    for i in range(lados):
        # Dividimos los 360 grados (2*PI) entre el número de lados
        angulo = 2 * math.pi * i / lados
        x = radio * math.cos(angulo)
        y = radio * math.sin(angulo)
        vertices.append((x, y, 0))
        
    # 5. Definición de aristas (Conexión de puntos)
    for i in range(lados):
        # Conecta el vértice actual con el siguiente. 
        # El '%' (módulo) asegura que el último se conecte con el primero.
        aristas.append((i, (i + 1) % lados))
        
    # 6. Cargar los datos a la malla de Blender
    malla.from_pydata(vertices, aristas, [])
    malla.update()

# 7. Llamada a la función (Ejemplo: Hexágono de radio 5)
crear_poligono_2d("Poligono2D", lados=6, radio=5)
```
A continuación se muestra el código en ejecución:

<img width="1920" height="1008" alt="Captura de pantalla 2026-02-25 202238" src="https://github.com/user-attachments/assets/6a829640-df36-4f6f-b0d7-207f910ce733" />

---

## 1.6 Procesamiento de Mapas de Bits
El procesamiento implica la manipulación directa de la matriz de píxeles:
* **Filtros de Convolución:** Aplicación de matrices (kernels) para realizar efectos como desenfoque, enfoque o detección de bordes.
* **Transformaciones de Color:** Ajuste de histogramas, brillo, contraste y conversión de imágenes a escala de grises o binarias (umbralización).
* **Histograma de imagen:** Representación gráfica de la distribución de intensidades de color en una imagen.

---

---

## 📚 Bibliografías y Fuentes de Consulta 

Antecedentes y evolución de la graficación por computadora. (s. f.). https://grafidepc.blogspot.com/p/blog-page.html

Área de aplicación de la graficación por computadora. (s. f.). https://grafidepc.blogspot.com/p/area-de-aplicacion-de-la-graficacion.html

Valdes, A. S. (2013, 14 septiembre). 1.4 Aspectos matemáticos de la Graficación (Geometría fractal). https://graficacionito.blogspot.com/2013/09/14-aspectos-matematicos-de-la.html

Modelos de color RGB, CMY, HSV y HSL. (s. f.). https://graficaciontmmjc.blogspot.com/2019/03/modelos-de-color-rgb-cmy-hsv-y-hsl.html

Valdes, A. S. (2013b, septiembre 22). 2.2  Representación y trazo de poligonos. https://graficacionito.blogspot.com/2013/09/22-representacion-y-trazo-de-poligonos.html

Client challenge. (s. f.). https://es.slideshare.net/slideshow/1-6-procesamiento-de-mapas-de-bits-en-graficacion/282295902

---

---
  
