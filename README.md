# SmartTakeoff (MVP web)

![Captura](docs/captura.png)

Abre `index.html` con Chrome o Edge (doble clic). No necesita internet ni instalación; los planos no salen de tu equipo.

## App de escritorio (Windows)
- Cada pull request y cada etiqueta `v*` generan el instalador **SmartTakeoff Setup.exe** con GitHub Actions (workflow *Desktop app (Windows)*).
- Para una versión oficial: crea un *release* con una etiqueta como `v0.5.0` y el instalador se adjunta solo.
- Para probar en tu PC con Node instalado: `npm install` y luego `npm start`.

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

## Estimado, precios y propuesta
- Cada condición y cada material del ensamble tienen **horas de mano de obra por unidad**. Los valores que trae son solo de referencia; ajústalos a tu empresa.
- La pestaña **Estimado** calcula materiales, impuesto, mano de obra (horas × tarifa), overhead, utilidad y el total de la oferta, con desglose por sistema.
- **Exportar/Importar lista de precios**: descarga un Excel con todos los materiales, llena precios y horas, y vuelve a cargarlo.
- **Generar propuesta** abre una propuesta lista para imprimir o guardar como PDF, con alcance por sistema, inclusiones, exclusiones y firmas.
- El Excel incluye la hoja **Estimate** con fórmulas vivas.

## Hojas, snap, deducciones y filtros
- **Varios PDF en un proyecto**: usa **+ PDF** en *Hojas*. Cada hoja toma su número del cuadro de rótulo (M-101, P-201…); doble clic para renombrarla.
- **Snap (S)**: ajusta los clics a esquinas y líneas del plano y a los puntos de otras mediciones.
- **Deducir (D)**: dibuja un hueco dentro de un área (shafts, columnas) y se resta solo.
- **Filtros**: el punto junto a cada condición la muestra u oculta en el plano; el control *Marcas* cambia la opacidad.

## Revisión y anotaciones
- **Anotar…**: nube (R), texto (T), flecha (W), callout (Q), resaltado (H), sello (M: Approved, Reviewed, Revise & Resubmit, Rejected, Field Verify, Not in Contract) y foto (F). Doble clic en una foto para verla, o en un texto/callout para editarlo.
- **PDF con marcas**: descarga todas las hojas con las mediciones, anotaciones y una leyenda de cantidades por hoja.
- **Comparar revisión**: elige el PDF de la nueva revisión; la hoja se empareja por su número y se muestran en rojo las líneas que desaparecen y en azul las nuevas. **Usar la revisión** cambia el plano de la hoja y conserva tus mediciones.

## Guardar en OneDrive o Dropbox

- **Guardar** (Ctrl+S) crea un archivo `.takeoff` con todo el proyecto: mediciones, condiciones, precios y los planos PDF incluidos. Elige una carpeta de OneDrive, Dropbox o Google Drive y se sincroniza sola entre tus equipos.
- Desde ese momento la app guarda los cambios automáticamente en ese mismo archivo (abajo verás "Guardado" con la hora). Ctrl+Shift+S guarda una copia con otro nombre.
- **Abrir proyecto** o arrastrar un `.takeoff` a la ventana lo abre con sus planos. En la versión de escritorio, doble clic en el archivo.
- El autoguardado directo funciona en Chrome y Edge. En Safari o Firefox, Guardar descarga el `.takeoff` y tú lo mueves a la carpeta.

## Condiciones
Cada condición define sistema, material, tamaño, forma de ducto (ancho×alto o diámetro), largo de pieza, separación de soportes, % de desperdicio y precio unitario.
Puedes editar la hoja *Condiciones* del Excel exportado y volver a cargarla con **Importar**.

## Atajos
V seleccionar · K calibrar · L lineal · A área · C conteo · R nube · T texto · Supr borrar · Ctrl+Z / Ctrl+Y · rueda = zoom · arrastrar o Espacio+arrastrar = desplazar · RePág/AvPág = páginas · Ctrl+S guardar proyecto.

El trabajo se guarda solo en el navegador por nombre de plano; usa **Guardar** para tener un respaldo `.takeoff.json`.
