# SmartTakeoff (MVP web)

![Captura](docs/captura.png)

Abre `index.html` con Chrome o Edge (doble clic). No necesita internet ni instalación; los planos no salen de tu equipo.

## Flujo básico
1. **Abrir PDF** (o arrastra el plano a la ventana).
2. **Escala:** elige una del menú (1/4"=1'-0", 1:50…) o usa **Calibrar (K)** y haz clic en los extremos de una cota conocida.
3. Elige una **condición** a la izquierda (ducto, tubería, difusor…) y mide:
   - **Lineal (L):** clic por punto, doble clic o Enter para terminar. Shift = ortogonal / 45°.
   - **Área (A):** clic en cada vértice, Enter para cerrar.
   - **Conteo (C):** clic en cada elemento, Enter para cerrar el grupo.
4. **Nube (R)** y **Texto (T)** para anotaciones de revisión.
5. Pestaña **Resumen / despiece**: piezas comerciales, lámina de ducto (ft²/m²), soportes y costo.
6. **Exportar Excel** (hojas Resumen, Detalle, Condiciones, Info), **CSV** o **Copiar para Excel**.

## Proyectos en EE. UU.
Las condiciones de ejemplo usan términos de obra de EE. UU. (Supply/Return Duct, Copper Type L, PEX, Black Steel Sch 40, PVC DWV, Cast Iron No-Hub, VAV Box…).
Los ductos calculan **calibre** automático (aprox. SMACNA baja presión) y **peso de lámina galvanizada en lb**. El Excel puede exportarse **en inglés** (LF, SF, EA) para contratistas.
La interfaz está **en inglés** por defecto; cambia a español con el selector de idioma de la barra superior.

## Codos, risers y lista de materiales
- Los **codos** se cuentan solos en cada quiebre de una línea (45° o 90°) y se marcan con un círculo en el plano.
- En la tabla *Detalle* puedes sumar **Vertical** (risers/drops en ft) y el número de **Drops**; cada drop suma un codo de 90°.
- Cada condición tiene un **ensamble**: materiales que salen solos con un factor (por LF, por ft² de lámina, por soporte, por codo, por tramo o por drop).
- La pestaña **Materiales** (Bill of Materials) junta todo y se exporta a Excel junto con la hoja *Ensambles*, que puedes editar y volver a importar.

## Condiciones
Cada condición define sistema, material, tamaño, forma de ducto (ancho×alto o diámetro), largo de pieza, separación de soportes, % de desperdicio y precio unitario.
Puedes editar la hoja *Condiciones* del Excel exportado y volver a cargarla con **Importar**.

## Atajos
V seleccionar · K calibrar · L lineal · A área · C conteo · R nube · T texto · Supr borrar · Ctrl+Z / Ctrl+Y · rueda = zoom · arrastrar o Espacio+arrastrar = desplazar · RePág/AvPág = páginas · Ctrl+S guardar proyecto.

El trabajo se guarda solo en el navegador por nombre de plano; usa **Guardar** para tener un respaldo `.takeoff.json`.
