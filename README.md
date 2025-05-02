# Visualización de Departamentos de Colombia a partir de un GeoJSON

> **Autor:** Fabián Andrés Huertas Reyes  
> **Fecha:** 2 de mayo de 2025  
> **Archivo principal:** `Colombia_Json.ipynb`  

## 📋 Descripción

Este notebook muestra, de forma sencilla y reproducible, cómo:

1. Montar Google Drive en Google Colab para acceder a datos almacenados en la nube.  
2. Cargar un archivo **GeoJSON** con la división político-administrativa de Colombia (departamentos).  
3. Dibujar el mapa del país, colorear los polígonos y **etiquetar** cada departamento con su nombre.  

El resultado es un mapa estático (figura de Matplotlib) listo para incluir en informes, presentaciones o dashboards.

---

## 🗃️ Estructura de carpetas sugerida
```
/
├─ Colombia_Json.ipynb        # Notebook principal
└─ drive/
   └─ MyDrive/
      └─ Mapa_Colombia_Json/
         └─ colombia_departamentos.geojson  # Fuente de datos
```

> ⚠️  Ajusta la variable `ruta_geojson` si decides colocar el archivo GeoJSON en otra ubicación.

---

## ⚙️ Requisitos

| Paquete        | Versión recomendada | Notas                             |
|----------------|---------------------|-----------------------------------|
| Python         | ≥ 3.9               | Colab ya incluye Python 3.10      |
| geopandas      | ≥ 0.14              | Instala dependencias de GDAL      |
| shapely        | ≥ 2.0               | Se instala con GeoPandas          |
| matplotlib     | ≥ 3.8               | Graficación estática              |
| fiona / pyproj | Automático          | Se instalan con GeoPandas         |

En Colab solo necesitas ejecutar:

```python
!pip install --quiet geopandas
```

---

## 🚀 Ejecución paso a paso

1. **Abrir** el notebook en Google Colab.  
2. Ejecutar la celda **“Montar acceso Google Drive”** y otorgar permisos.  
3. Verificar/editar la ruta del archivo en la celda **“Ruta de archivo Json de Colombia”**.  
4. Ejecutar la celda **“Lectura del archivo Json y visualización en el mapa”**.  
5. Se mostrará el mapa con los nombres de los 32 departamentos.  

> 💡 Para **guardar** la figura, añade `plt.savefig('mapa_colombia_departamentos.png', dpi=300)` antes de `plt.show()`.

---

## 🎨 Personalización rápida

| Elemento                | Cómo cambiarlo                                                      |
|-------------------------|---------------------------------------------------------------------|
| Color de los polígonos  | Modifica el parámetro `color='lightblue'` en `departamentos.plot()` |
| Grosor del borde        | `edgecolor='black', linewidth=0.8`                                  |
| Fuente/estilo de texto  | Ajusta `fontsize`, `color` y `ha` en el bucle `ax.text()`           |
| Título                  | Cambia el texto en `ax.set_title()`                                 |

---

## 🛠️ Posibles extensiones

* Exportar el mapa a **PNG** o **PDF** para su uso en informes.  
* Generar una versión interactiva con **Folium** o **Plotly**.  
* Superponer capas adicionales (capitales, ríos, carreteras).  
* Aplicar un efecto pseudo-3D usando `geopandas` + `mpl_toolkits.mplot3d`.  

---

## 📝 Licencia de datos

El GeoJSON de departamentos proviene de fuentes abiertas (por ejemplo, [IGAC](https://www.igac.gov.co/) o repositorios de GitHub).  
Verifica siempre los términos originales antes de redistribuir el archivo.

---

## 🤝 Contribuciones

1. Haz un *fork* del repositorio.  
2. Crea tu rama de mejoras: `git checkout -b feature/mi-mejora`.  
3. Confirma cambios: `git commit -m "Añade leyenda"`  
4. Envía un *pull request*.

---

## 📮 Contacto

Si encuentras problemas o tienes sugerencias, abre un *issue* o escríbeme a **fabian@nepturalabs.net**.

¡Disfruta visualizando los datos geográficos de Colombia! 🇨🇴
