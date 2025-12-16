# 🌓 Funcionalidad de Modo Claro/Oscuro

## ✨ Características Implementadas

El portafolio ahora cuenta con un sistema completo de alternancia entre modo oscuro y modo claro:

### 🎯 Funcionalidades

1. **Botón de Alternancia**
   - Ubicado en la navbar superior derecha
   - Icono 🌙 para modo oscuro (default)
   - Icono ☀️ para modo claro
   - Animación de rotación al hacer clic

2. **Persistencia de Preferencias**
   - Guarda la preferencia del usuario en `localStorage`
   - Mantiene el tema seleccionado entre sesiones
   - Detecta automáticamente la preferencia del sistema operativo

3. **Sin Parpadeo (FOUC Prevention)**
   - Script inline que aplica el tema antes de renderizar
   - Transición suave entre temas (0.3s)
   - Experiencia fluida al cargar la página

4. **Temas Completos**
   
   **Modo Oscuro (Default):**
   - Fondo: #0a0a0a y #1a1a1a
   - Texto: #f5f5f5
   - Acentos: #f4a261 y #e76f51
   - Perfecto para trabajo nocturno

   **Modo Claro:**
   - Fondo: #ffffff y #f5f5f5
   - Texto: #1a1a1a
   - Acentos: #e76f51 y #f4a261
   - Ideal para ambientes con luz

### 🎨 Elementos Adaptados

Todos los componentes principales se adaptan automáticamente:

- ✅ Navbar con glassmorphism adaptado
- ✅ Hero Section con gradientes ajustados
- ✅ Sección de Experiencia
- ✅ Showcase de Proyectos
- ✅ Stack Tecnológico
- ✅ Sección de Contacto
- ✅ Footer
- ✅ Loader inicial

### 🔧 Implementación Técnica

**Variables CSS Dinámicas:**
```css
:root {
  --background: #0a0a0a;
  --text-primary: #f5f5f5;
  /* ... más variables */
}

html.light-mode {
  --background: #ffffff;
  --text-primary: #1a1a1a;
  /* ... variables modificadas */
}
```

**JavaScript:**
- Detecta preferencia guardada o del sistema
- Aplica clase `.light-mode` al elemento `<html>`
- Guarda cambios en `localStorage`
- Animación suave del botón

### 📱 Responsividad

El cambio de tema funciona perfectamente en:
- 🖥️ Desktop (1920px+)
- 💻 Laptop (1024px+)
- 📱 Tablet (768px+)
- 📱 Móvil (320px+)

### 🚀 Uso

1. **Cambiar tema manualmente:**
   - Hacer clic en el botón 🌙/☀️ en la navbar

2. **Tema automático:**
   - La primera visita detecta tu preferencia del sistema
   - Visitas subsecuentes usan tu última selección

3. **Resetear preferencia:**
   ```javascript
   localStorage.removeItem('theme');
   location.reload();
   ```

### 💡 Ventajas

- ⚡ Rendimiento óptimo (sin JavaScript externo)
- 🎯 Accesibilidad mejorada
- 💾 Experiencia personalizada persistente
- 🎨 Diseño profesional en ambos modos
- 🔄 Transiciones suaves y elegantes

### 🎨 Paleta de Colores

**Modo Oscuro:**
- Background: `#0a0a0a`, `#1a1a1a`
- Primary Text: `#f5f5f5`
- Secondary Text: `#b0b0b0`
- Accent: `#f4a261`, `#e76f51`

**Modo Claro:**
- Background: `#ffffff`, `#f5f5f5`
- Primary Text: `#1a1a1a`
- Secondary Text: `#666666`
- Accent: `#e76f51`, `#f4a261`

---

**Desarrollado con ❤️ por Ivan Asdrubal Villegas Espinosa**
