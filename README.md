# 🔍 Simbolismo en el Espacio — PWA Educativa

**Agencia de Análisis Psicológico Visual (AAPV)**  
Misión: Detectives del Simbolismo Visual — Edición "Héroes y Distopías"

---

## 📋 Descripción

Aplicación web progresiva (PWA) gamificada para estudiantes de educación superior, diseñada para analizar **Afiches Alternativos de Películas (AMPs)** mediante el **mapa espacial de Max Pulver**. Los estudiantes adoptan el rol de agentes de la AAPV y decodifican mensajes ocultos en afiches de cine, aplicando un protocolo de análisis psicológico-visual basado en cinco zonas espaciales:

| Zona | Significado |
|------|-------------|
| **Centro** | El "Yo", el presente, la identidad |
| **Superior** | Intelecto, idealismo, misticismo, poder |
| **Inferior** | Instintos, motricidad, materia, destrucción |
| **Izquierda** | Pasado, origen, introversión, regresión |
| **Derecha** | Futuro, avance, audacia, extraversión |

---

## 🚀 Cómo usar

1. **Abrir el archivo** `simbolismo_en_el_espacio.html` en cualquier navegador moderno (Chrome, Edge, Firefox, Safari).
2. **Registrarse** como agente ingresando nombre, apellidos y correo electrónico válido.
3. **Acceder al sistema** tras la secuencia de boot tipo terminal.
4. **Seleccionar un expediente** desde el dashboard (Matrix, Superman, Terminator, El Quinto Elemento).
5. **Completar el Protocolo de Decodificación Pulver**:
   - Explorar los 5 hotspots interactivos sobre el afiche
   - Responder las preguntas de orientación, posición del título y palabra clave
   - Contestar el cuestionario con preguntas cerradas y abiertas
6. **Generar el PDF** con todas las respuestas al finalizar.

> 💡 **Instalación como app:** En Chrome/Edge, haz clic en "Instalar Simbolismo en el Espacio" desde el menú del navegador para usarla como aplicación nativa.

---

## 📁 Estructura del proyecto

```
simbolismo_en_el_espacio.html   (único archivo, ~1.82 MB)
├── HTML5 semántico
├── CSS3 con variables CSS y temas dinámicos
├── JavaScript vanilla (arquitectura MVC simulada)
├── Bootstrap 5.3.2 (CDN)
├── Bootstrap Icons 1.11.1 (CDN)
├── html2pdf.js 0.10.1 (CDN)
├── Imágenes incrustadas en base64:
│   ├── Matrix (John Dunn)
│   ├── Superman (Jake Kontou)
│   ├── Terminator (Pablo Olivera)
│   └── El Quinto Elemento (Steve De La mare)
├── Service Worker inline (funcionamiento offline)
└── Manifest JSON inline (instalación PWA)
```

---

## 🎮 Funcionalidades

### Registro de agente
- Formulario con validación de campos obligatorios
- Validación de correo electrónico con expresión regular
- Datos persistentes en memoria para generación de PDF

### Hotspots interactivos (Mapa Pulver)
- 5 puntos interactivos por afiche, posicionados en porcentajes relativos
- **Fuera del contenedor con `overflow:hidden`** para garantizar visibilidad
- Tooltip global único (`#g-tip`) con `position:fixed` y `z-index:9999`
- Posicionamiento inteligente: arriba por defecto, abajo si no hay espacio, clamp a viewport
- Animación de pulso para atraer la atención del usuario

### Protocolo de Decodificación (5 pasos)
| Paso | Acción | Validación |
|------|--------|------------|
| 1 | Hackeo del Sistema (tráiler) | Automático |
| 2 | Escaneo de Orientación | Select con retroalimentación |
| 3 | Inventario de Símbolos | 3+ hotspots explorados |
| 4 | Rastreo del Título | Select con retroalimentación |
| 5 | Sello de la Matriz | Input con validación on-the-fly |

### Cuestionario del Agente
- **P1 (Cerrada):** Motivación principal del protagonista
- **P2 (Cerrada):** Significado de la zona superior
- **P3 (Abierta):** Análisis de tensión pasado/futuro (mín. 30 palabras, contador en tiempo real)
- Retroalimentación inmediata con indicadores ✓/✗

### Generación de PDF
- Incluye datos del agente, fecha, todas las respuestas de los 4 expedientes
- Indicadores de corrección por pregunta
- Formato A4, calidad de imagen optimizada

### Temas visuales intercambiables
- **Default:** Verde cibernético (AAPV)
- **Matrix:** Código verde
- **Superman:** Dorado y rojo heroico
- **Terminator:** Rjo distópico
- **El Quinto Elemento:** Naranja cósmico

### Navegación táctil
- Swipe izquierdo: avanzar al siguiente expediente (futuro/progreso)
- Swipe derecho: retroceder al expediente anterior (pasado/regresión)

### Polling simulado
- Actualización periódica cada 10 segundos vía `setInterval`
- Simula `Ajax.PeriodicalUpdater` del patrón push-pull

---

## 🏗️ Arquitectura técnica

| Capa | Tecnología | Simbolismo Pulver |
|------|-----------|-------------------|
| **Vista** | HTML5 + CSS3 | Zona Central (el "Yo", el presente) |
| **Controlador** | JavaScript vanilla + AJAX mock | Zona Derecha (extraversión, iniciativa, futuro) |
| **Modelo** | Datos JSON en memoria | Zona Inferior/Izquierda (origen, memoria, materia) |

### Patrón MVC
- **Vista:** Representa la "Forma" y el presente. CSS permite diseños orgánicos y flexibles.
- **Controlador:** Motor de la PWA. Gestiona eventos y comunicación en tiempo real sin recargar la página.
- **Modelo:** Almacena afiches, usuarios, perfiles y progreso de decodificación.

### AJAX simulado
- `XMLHttpRequest` mock con métodos `open()`, `send()`, `onreadystatechange`
- Respuestas en JSON con delay simulado de red (600–1400ms)
- Callbacks: `onSuccess`, retroalimentación visual con radar de carga

---

## 📱 Compatibilidad

| Plataforma | Estado |
|-----------|--------|
| Chrome (escritorio/móvil) | ✅ Completo |
| Edge (escritorio/móvil) | ✅ Completo |
| Firefox | ✅ Completo |
| Safari (iOS/macOS) | ✅ Completo |
| Instalación como app | ✅ Chrome/Edge/Safari |
| Funcionamiento offline | ✅ Tras primera carga |

---

## 🛠️ Tecnologías utilizadas

- **HTML5** — Estructura semántica, metatags PWA
- **CSS3** — Variables CSS, Grid, Flexbox, animaciones, media queries
- **JavaScript (ES6+)** — Módulos lógicos, eventos DOM, AJAX mock
- **Bootstrap 5.3.2** — Sistema de grid, componentes, utilidades
- **Bootstrap Icons 1.11.1** — Iconografía universal
- **html2pdf.js 0.10.1** — Generación de PDF desde HTML
- **Service Worker** — Cacheo de recursos para offline
- **Web App Manifest** — Instalación nativa en dispositivos

---

## 📄 Licencia y créditos

**Proyecto educativo** desarrollado para estudiantes de educación superior.

**Afiches analizados:**
- *The Matrix* — John Dunn (@johndunn_art)
- *Superman* — Jake Kontou (@jakekontou)
- *The Terminator* — Pablo Olivera (Behance: pabloolivera)
- *The Fifth Element* — Steve De La mare (@stevedelamare)

**Marco teórico:** Mapa espacial de Max Pulver (grafología y psicología del espacio).

---

## 🔧 Notas técnicas para desarrolladores

### Hotspots y tooltip
Los hotspots (`.hs`) son elementos posicionados absolutamente dentro de `.stage-wrap` (hermanos de `.stage-img-wrap`, no hijos). Esto garantiza que:
- `.stage-img-wrap` puede tener `overflow:hidden` sin afectar la visibilidad de los hotspots
- Los hotspots mantienen `z-index:100` para superponerse sobre la imagen
- El tooltip global `#g-tip` usa `position:fixed` para evitar cualquier clipping del DOM

### Generación de PDF
El botón de PDF utiliza `html2pdf.js` que renderiza el DOM a canvas y luego a PDF. El contenido se prepara dinámicamente en un div oculto (`#pdf-content`) con estilos optimizados para impresión.

### Temas CSS
Los temas se aplican mediante clases en `<body>` que sobrescriben variables CSS. La transición es inmediata sin recarga de página.

---

*"El futuro y el progreso se empujan hacia la derecha, mientras que el choque instintivo y biológico de estas distopías se representa de forma universal en la zona material inferior."*

— **Conclusión del Protocolo Pulver, AAPV**
