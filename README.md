<h1 align="center">🗺️ Simulador de Examen - Sistemas de Información Geográfica (SIG)</h1>

<div align="center">
    <a href="https://agussantinelli.github.io/sig-parcial" target="_blank"> 
         <img src="https://img.shields.io/badge/Live-Page-blue?style=for-the-badge&logo=githubpages&logoColor=white" alt="Live Page"/>
    </a>
    <a href="https://github.com/agussantinelli/sig-parcial" target="_blank" style="text-decoration: none;">
        <img src="https://img.shields.io/badge/💻%20Repo%20Principal-sig--parcial-0b7285?style=for-the-badge&logo=github&logoColor=white" alt="Repo SIG Parcial"/>
    </a>
</div>

<p align="center">
    <a href="https://github.com/agussantinelli" target="_blank" style="text-decoration: none;">
        <img src="https://img.shields.io/badge/👤%20Agustín%20Santinelli-agussantinelli-000000?style=for-the-badge&logo=github&logoColor=white" alt="Agus"/>
    </a>
</p>

<p align="center">
    <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5 Badge"/>
    <img src="https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript Badge"/>
    <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS Badge"/>
    <img src="https://img.shields.io/badge/CSS3-Media_Queries-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3 Badge"/>
    <img src="https://img.shields.io/badge/GitHub_Actions-CI%2FCD-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" alt="GitHub Actions Badge"/>
    <img src="https://img.shields.io/badge/GitHub_Pages-222222?style=for-the-badge&logo=githubpages&logoColor=white" alt="GitHub Pages Badge"/>
</p>
<hr>

<h2>🎯 Objetivo y Alcance</h2>

<p>
    <strong>Simulador de Examen Parcial SIG</strong> es una aplicación web interactiva de entrenamiento y evaluación diagnóstica, diseñada específicamente para preparar a los estudiantes en los conceptos teóricos y prácticos clave de la cátedra de <strong>Sistemas de Información Geográfica (SIG)</strong>.
</p>

<p>
    La plataforma permite contestar un banco curado de <strong>45 preguntas en simultáneo y sin orden fijo</strong>, simulando las condiciones reales de examen donde cada enunciado presenta afirmaciones múltiples (A, B, C y/o D) y requiere evaluar críticamente su veracidad sin pistas previas.
</p>

<ul>
    <li><strong>Geodesia y Modelos de la Tierra:</strong> Geoide, elipsoide de referencia, datum local y geocéntrico (WGS 84, POSGAR, CTRS/ITRS) y declinación magnética vs convergencia de cuadrícula.</li>
    <li><strong>Sistemas de Coordenadas y Proyecciones:</strong> Coordenadas geográficas y proyectadas, distorsiones cartográficas, Gauss-Krüger argentino (7 fajas de 3°, falso este 500.000 m), Mercator y proyecciones acimutales.</li>
    <li><strong>Modelos y Formatos de Datos:</strong> Formato vectorial (puntos, líneas, polígonos, .shp, GeoPackage, KML, GeoJSON) vs ráster/matricial (celdas, altimetría, GeoTIFF, teledetección).</li>
    <li><strong>Infraestructuras de Datos Espaciales (IDE):</strong> Principios de interoperabilidad, estándares del OGC (WMS, WFS, WCS, CSW, SLD), metadatos institucionales y visualizadores vs geoportales.</li>
    <li><strong>Herramientas y Casos de Aplicación:</strong> Operaciones en QGIS (calculadora de campos, importación CSV), gestión pública, geomarketing, redes de infraestructura (utilities) y mapas de calor en seguridad ciudadana.</li>
</ul>

<hr>

<h2>⚙️ Stack Tecnológico</h2>

 <table>
  <thead>
   <tr>
    <th>Componente</th>
    <th>Tecnología</th>
    <th>Versión / Detalles</th>
   </tr>
  </thead>
  <tbody>
   <tr>
    <td><strong>Frontend Web</strong></td>
    <td>HTML5 Semántico + JavaScript Vanilla (ES6+)</td>
    <td>Arquitectura Single Page Application (SPA) 100% estática, ligera y sin dependencias externas pesadas.</td>
   </tr>
   <tr>
    <td><strong>Estilos y Diseño</strong></td>
    <td>Tailwind CSS (CDN) + Vanilla CSS3</td>
    <td>Diseño moderno con microanimaciones, sistema tipográfico Inter y estilos visuales personalizados.</td>
   </tr>
   <tr>
    <td><strong>Adaptabilidad</strong></td>
    <td>CSS Media Queries Avanzadas</td>
    <td>Breakpoints específicos para móviles pequeños, tablets, laptops, monitores anchos y hojas de estilo para impresión.</td>
   </tr>
   <tr>
    <td><strong>Algoritmo de Aleatorización</strong></td>
    <td>Fisher-Yates Shuffle</td>
    <td>Mezcla 100% aleatoria de las 45 preguntas en cada inicio y reinicio de la sesión.</td>
   </tr>
   <tr>
    <td><strong>Motor de Evaluación</strong></td>
    <td>Evaluación Estricta Multi-Opción</td>
    <td>Calificación <i>all-or-nothing</i> (+1 pt con 100% de aciertos sin fallos; 0 pts con casilla en amarillo para estudio).</td>
   </tr>
   <tr>
    <td><strong>Despliegue Continuo (CI/CD)</strong></td>
    <td>GitHub Actions + GitHub Pages</td>
    <td>Pipeline de integración continua automatizado que publica los cambios en vivo en cada push a la rama <code>main</code>.</td>
   </tr>
  </tbody>
 </table>

<hr>

<h2>🏗️ Arquitectura de la Solución</h2>

 <p>La solución está estructurada bajo el patrón de <strong>Single Page Application (SPA) client-side</strong>, garantizando reactividad instantánea sin requerir backend ni base de datos remota:</p>

 <ul>
     <li><strong>Capa de Presentación e Interacción:</strong>
         <ul>
             <li>Carga directa de las 45 preguntas sin pantallas intermedias ni bloqueos.</li>
             <li>Selector de vista dual: <strong>"Todas simultáneas"</strong> (vista de lista completa) o <strong>"Una por una"</strong> (modo enfocado con navegación asistida).</li>
             <li>Casillas interactivas A, B, C y D con selección múltiple o individual libre y botón explícito <strong>"Enviar respuestas"</strong>.</li>
             <li>Botón flotante (FAB) interactivo en dispositivos móviles para acceder rápidamente al mapa de preguntas.</li>
         </ul>
     </li>
     <li><strong>Capa de Lógica de Evaluación:</strong>
         <ul>
             <li>Validación instantánea al enviar: resalta en verde las opciones correctas marcadas, en amarillo discontinuo las que faltaron marcar y en rojo los errores.</li>
             <li><strong>Regla estricta:</strong> Solo suma 1 punto si se marcan exactamente todas las correctas sin fallos. Si hubo aciertos parciales, suma 0 puntos pero marca la casilla en <strong>amarillo</strong> en el mapa para guiar el estudio.</li>
             <li>Despliegue inmediato de la justificación y explicación oficial elaborada para cada pregunta.</li>
         </ul>
     </li>
     <li><strong>Capa de Navegación y Mapa Visual (Sidebar):</strong>
         <ul>
             <li>Mapa interactivo de 45 casillas con sincronización bidireccional en tiempo real.</li>
             <li>Código de estados por color: <strong>Gris</strong> (Pendiente), <strong>Verde</strong> (Perfecta +1 pt), <strong>Amarillo</strong> (Incompleta 0 pts) y <strong>Rojo</strong> (Incorrecta 0 pts).</li>
             <li>Barra de filtros dinámicos (Todas, Pendientes, Perfectas, Incorrectas) y salto a la siguiente pregunta no respondida.</li>
             <li>Acción rápida de reordenamiento aleatorio (<strong>"🔀 Mezclar"</strong>) y reinicio general con modal de resultados y porcentaje.</li>
         </ul>
     </li>
 </ul>

<hr>

<h2>📂 Estructura del Proyecto</h2>

<pre><code>sig-parcial/
├── .github/
│   └── workflows/
│       └── deploy.yml       # Pipeline automatizado de CI/CD para GitHub Pages
├── index.html               # Aplicación principal SPA (Punto de entrada para el despliegue)
└── README.md                # Documentación técnica y académica del repositorio
</code></pre>

<hr>

<h2>🧩 Funcionalidades Principales</h2>

<ul>
    <li><strong>Resolución Libre y Simultánea</strong>
        <ul>
            <li>Posibilidad de responder cualquier pregunta en el orden deseado sin restricciones secuenciales.</li>
        </ul>
    </li>
    <li><strong>Selección Multi-Opción Realista</strong>
        <ul>
            <li>Permite marcar una o más opciones (A, B, C y/o D) sin pistas que revelen la cantidad de respuestas válidas.</li>
        </ul>
    </li>
    <li><strong>Mapa Interactivo de 45 Preguntas</strong>
        <ul>
            <li>Navegación instantánea a cualquier tarjeta mediante scroll suave y resaltado visual con efecto glow.</li>
        </ul>
    </li>
    <li><strong>Puntuación Rigurosa con Casillas de Estudio</strong>
        <ul>
            <li>Visualización clara en el mapa de las preguntas resueltas a la perfección (verde) frente a las incompletas (amarillo).</li>
        </ul>
    </li>
    <li><strong>Orden 100% Aleatorio</strong>
        <ul>
            <li>Mezcla matemática con Fisher-Yates al abrir la app o mediante el botón de reordenamiento rápido.</li>
        </ul>
    </li>
    <li><strong>Totalmente Responsive</strong>
        <ul>
            <li>Adaptado con múltiples media queries para teléfonos móviles, tablets y pantallas de escritorio.</li>
        </ul>
    </li>
</ul>

<hr>

<h2>🚀 Puesta en Marcha (Setup Local)</h2>

<h3>1. Requisitos Previos</h3>
<p>No se requieren compiladores ni gestores de paquetes. Solo necesitás cualquier navegador web moderno (Chrome, Firefox, Edge, Safari).</p>

<h3>2. Ejecución Local</h3>

<ol>
    <li>Clonar el repositorio:
        <pre><code>git clone https://github.com/agussantinelli/sig-parcial.git</code></pre>
    </li>
    <li>Ingresar al directorio del proyecto:
        <pre><code>cd sig-parcial</code></pre>
    </li>
    <li>Abrir el simulador directamente en el navegador:
        <pre><code># En Windows
start index.html

# En macOS
open index.html

# En Linux
xdg-open index.html</code></pre>
    </li>
</ol>

<hr>

<h2>📚 Contexto Académico</h2>

<p>
    Este simulador fue desarrollado como herramienta de estudio y práctica para el examen parcial de la materia electiva <strong>Sistemas de Información Geográfica</strong> de la carrera <strong>Ingeniería en Sistemas de Información</strong> en la <strong>Universidad Tecnológica Nacional, Facultad Regional Rosario (UTN FRRO)</strong>.
</p>
<p>
    <strong>Docentes de la cátedra:</strong> Ricagno Andrés, Ascolani Federico.
</p>

<hr />

<h2 align="left">⚖️ Licencia</h2>

<p align="left">
  Este proyecto se distribuye bajo los términos de la <b>Licencia MIT</b>. 
  Permite el uso, copia, modificación y distribución de forma libre y gratuita con fines educativos o personales.
</p>

<hr />

<h2 align="left">🤝 Contribución</h2>

<p align="left">
  Si encontrás alguna errata en las preguntas o querés proponer mejoras:
  <ul>
    <li>Hacé un fork del repositorio.</li>
    <li>Creá una nueva rama para tus cambios (<code>git checkout -b feature/nueva-pregunta</code>).</li>
    <li>Realizá tus commits con claridad.</li>
    <li>Enviá un Pull Request para su revisión.</li>
  </ul>
</p>

<p align="left">
  ¡Éxitos en el parcial de SIG! 🗺️📊
</p>

<hr />

<p><em>Simulador de Examen SIG – Consolidando el conocimiento espacial a través de la práctica interactiva.</em></p>
