# 🎄 Calendario de Adviento Interactivo

Un calendario de Adviento digital elegante e interactivo con efectos visuales cautivadores, mensajes personalizados y una experiencia de usuario fluida.

## ✨ Características

### 🎁 Interactividad
- **Calendario interactivo** con 24 cajas clicables correspondientes a los días de Adviento
- **Bloqueo automático de días futuros** - Solo los días pasados y el actual (3 de diciembre) son accesibles
- **Contador de progreso visual** - Anillo circular que se llena conforme abres días
- **Mensajes personalizados** - Cada día tiene un mensaje único y poético almacenado en JSON

### 🎨 Efectos Visuales Impactantes
- **Animación de apertura de caja** - La tapa desaparece hacia arriba con efecto de escala y blur
- **Brillo dorado envolvente** - Glow intenso al abrir cada caja
- **Sparkles dorados** - Partículas de luz que caen elegantemente
- **Confeti colorido** - Animación de caída con rotación y múltiples colores
- **Gradiente animado en modal** - Fondo del modal con gradiente sutil que cambia suavemente

### 📱 Responsive y Mobile-Friendly
- **Diseño responsive** optimizado para desktop y móviles
- **Hover effects sutiles** - Visual feedback al pasar el mouse sobre cajas disponibles
- **Touch-friendly** - Interacciones optimizadas para dispositivos táctiles
- **Adaptive typography** - Tamaños de texto ajustados por dispositivo

### 🎵 Enlaces Inteligentes
- **Detección automática de URLs** en los mensajes
- **URLs de Spotify** convertidas a botones "🎵 Escúchame"
- **URLs generales** convertidas a enlaces "🔗 Abre esto"
- Apertura en nuevas pestañas

## 🛠️ Tecnologías Utilizadas

- **HTML5** - Estructura semántica
- **CSS3** - Animaciones keyframes, gradientes, glassmorphism
- **JavaScript (Vanilla ES6)** - Lógica interactiva sin dependencias
- **JSON** - Almacenamiento de mensajes externos
- **SVG** - Anillo de progreso circular

## 📁 Estructura del Proyecto

```
Calendario Adviento/
├── index.html          # Archivo principal con HTML, CSS y JS
├── messages.json       # Mensajes personalizados para cada día
└── resources/
    ├── 1.png          # Imagen del calendario (fondo)
    └── 2.png          # Imagen adicional
```

## 🎯 Cómo Usar

1. Abre `index.html` en tu navegador
2. Verás el calendario de Adviento con solo los días 1-3 disponibles (al 3 de diciembre)
3. Haz clic en cualquier caja disponible para:
   - Ver la animación de apertura dramática
   - Disfrutar de sparkles y confeti
   - Leer el mensaje personalizado del día
4. El contador en la esquina inferior derecha muestra tu progreso

## 🎬 Flujo de Animación

Cuando abres una caja:

```
0ms   → Inicia apertura de caja (scale 1.5, translateY -80px)
100ms → Sparkles dorados aparecen
300ms → Confeti multicolor cae
1000ms → Animación completa
2000ms → Modal con mensaje se abre
```

## 💾 Mensajes Personalizados

Los mensajes se cargan desde `messages.json` con la siguiente estructura:

```json
{
  "1": "Mensaje para el día 1",
  "2": "Mensaje para el día 2",
  ...
  "24": "¡Feliz Nochebuena! 🎄"
}
```

### Características de los Mensajes:
- Pueden incluir **URLs de Spotify** (se convierten automáticamente a botones)
- Pueden incluir **URLs generales** (se convierten a enlaces)
- **Soporte completo a emojis** y caracteres especiales
- **HTML sanitizado** automáticamente contra inyecciones

## 🎨 Personalización

### Cambiar la Fecha de Bloqueo
En `index.html`, línea ~738:
```javascript
const currentDay = 3; // Cambia 3 por otro día (1-24)
```

### Modificar Colores
Los colores principales están definidos en CSS:
- **Dorado**: `#fbbf24`
- **Rojo**: `#dc2626`
- **Verde**: `#10b981`
- **Azul**: `#3b82f6`

### Ajustar Duraciones de Animaciones
- Apertura de caja: `lidFade 1s`
- Brillo: `softGlow 1s`
- Sparkles: `2s`
- Confeti: `2.5-4s`

## 🎁 Efectos Especiales

### Animación de Apertura
- **lidFade**: Tapa que sube y desaparece con blur
- **softGlow**: Brillo dorado envolvente
- **innerSparkle**: Borde brillante que pulsa

### Partículas
- **Sparkles**: 12 partículas doradas por caja
- **Confeti**: 40 partículas con 4 colores diferentes
- **Snowflakes**: Decoración de fondo (opcional)

## 📊 Contador de Progreso

El anillo circular en la esquina inferior derecha:
- Muestra días abiertos / 24
- Se llena suavemente (0.5s transition)
- Cálculo: `circumference * (1 - progress)`
- Radio del anillo: 50px

## 🔧 Funciones Principales

| Función | Descripción |
|---------|-------------|
| `initCalendar()` | Inicializa cajas y event listeners |
| `loadMessages()` | Carga mensajes desde JSON |
| `showModal(day, title, message)` | Muestra modal con contenido |
| `createConfetti()` | Genera partículas de confeti |
| `createSparkles(x, y)` | Genera destellos dorados |
| `updateCounter()` | Actualiza anillo de progreso |
| `linkify(text)` | Convierte URLs en enlaces clicables |
| `escapeHtml(text)` | Sanitiza HTML para seguridad |

## 🌐 Compatibilidad

- ✅ Chrome/Edge 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Mobile Chrome/Safari

## 📝 Notas Técnicas

### Seguridad
- HTML escapado automáticamente en mensajes
- Prevención de inyección XSS con `escapeHtml()`
- Validación de URLs antes de renderizar

### Rendimiento
- Sin dependencias externas (0 bloat)
- CSS animations (GPU accelerated)
- Cleanup automático de particles
- Carga de mensajes asincrónica

### Accesibilidad
- Navegación por teclado (próxima versión)
- Atributos ARIA en modales
- Contraste de colores WCAG AA

## 🚀 Mejoras Futuras

- [ ] Sonido de apertura (Web Audio API)
- [ ] Animación de efecto parallax
- [ ] Guardado de progreso en localStorage
- [ ] Tema oscuro/claro
- [ ] Idiomas múltiples
- [ ] Compartir en redes sociales

## 📄 Licencia

Este proyecto es de código abierto y está disponible bajo la licencia MIT.

## 🤝 Créditos

Desarrollado con ❤️ como regalo digital navideño.

---

**¿Problemas?** Verifica que:
- ✅ `messages.json` esté en la misma carpeta que `index.html`
- ✅ Las imágenes en `resources/` estén presentes
- ✅ El navegador soporte CSS Grid y CSS animations
- ✅ JavaScript esté habilitado en el navegador
