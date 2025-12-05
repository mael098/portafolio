# 🚀 Portafolio Profesional - Ivan Asdrubal Villegas Espinosa

Portafolio profesional de Ingeniero en Sistemas Computacionales construido con **Astro**, diseñado con estándares de la industria y optimizado para rendimiento.

## ✨ Características

- 🎨 **Diseño Moderno y Profesional**: Interfaz oscura con gradientes y animaciones suaves
- 📱 **Totalmente Responsive**: Optimizado para todos los dispositivos
- ⚡ **Alto Rendimiento**: Construido con Astro para carga ultra-rápida
- 🎯 **Secciones Clave**:
  - Hero profesional con código interactivo
  - Experiencia laboral con timeline
  - Proyectos desplegados con enlaces en vivo
  - Stack tecnológico con niveles de habilidad
  - Certificaciones y logros
  - Contacto con redes sociales

## 🛠️ Tecnologías

- [Astro](https://astro.build/) - Framework estático
- TypeScript
- CSS moderno con gradientes y animaciones
- Diseño mobile-first

## 📦 Instalación

```bash
# Instalar dependencias
npm install

# Modo desarrollo
npm run dev

# Construir para producción
npm run build

# Vista previa de producción
npm run preview
```

## 🎨 Personalización

### 1. Información Personal

Edita `src/components/HeroProfessional.astro`:

```typescript
const socialLinks = [
  {
    name: "GitHub",
    url: "TU_GITHUB",
    icon: "github"
  },
  {
    name: "LinkedIn",
    url: "TU_LINKEDIN",
    icon: "linkedin"
  },
  {
    name: "Email",
    url: "mailto:TU_EMAIL",
    icon: "email"
  }
];
```

### 2. Proyectos Desplegados

Edita `src/components/ProjectShowcase.astro`:

```typescript
const projects: Project[] = [
  {
    title: "Nombre del Proyecto",
    description: "Descripción técnica detallada...",
    image: "/imagen.jpg",
    technologies: ["React", "Node.js", "PostgreSQL"],
    liveUrl: "https://tu-proyecto.com",
    githubUrl: "https://github.com/usuario/proyecto",
    category: "fullstack",
    featured: true
  },
  // Agregar más proyectos...
];
```

### 3. Stack Tecnológico

Edita `src/components/TechStack.astro`:

```typescript
const skills = {
  frontend: [
    { name: "React", level: 90, icon: "⚛️" },
    // Personaliza tus habilidades...
  ],
  backend: [
    { name: "Node.js", level: 90, icon: "🟢" },
    // Personaliza tus habilidades...
  ],
  // Más categorías...
};
```

### 4. Experiencia Laboral

Edita `src/components/Experience.astro`:

```typescript
const experience = [
  {
    role: "Tu Rol",
    company: "Empresa",
    period: "2023 - Presente",
    description: "Descripción del rol...",
    achievements: [
      "Logro 1",
      "Logro 2",
      "Logro 3"
    ],
    technologies: ["Tech1", "Tech2"]
  },
  // Más experiencia...
];
```

### 5. Certificaciones

Edita las certificaciones en `src/components/TechStack.astro`:

```typescript
const certifications = [
  {
    title: "Certificación",
    issuer: "Emisor",
    year: "2024"
  },
  // Más certificaciones...
];
```

### 6. Colores y Tema

Personaliza los colores en `src/pages/_estilos.css`:

```css
:root {
  --primary: #0a0a0a;
  --secondary: #1a1a1a;
  --accent: #f4a261;        /* Color de acento principal */
  --accent-dark: #e76f51;   /* Color de acento oscuro */
  /* Personaliza más colores... */
}
```

## 📁 Estructura del Proyecto

```
portafolio/
├── public/               # Archivos estáticos (imágenes, CV, etc.)
├── src/
│   ├── components/       # Componentes reutilizables
│   │   ├── HeroProfessional.astro
│   │   ├── ProjectShowcase.astro
│   │   ├── TechStack.astro
│   │   ├── Experience.astro
│   │   └── Card.astro
│   ├── layouts/
│   │   └── Layout.astro  # Layout principal
│   ├── pages/
│   │   ├── index.astro   # Página principal
│   │   └── _estilos.css  # Estilos globales
│   └── styles/
│       └── global.css    # Estilos adicionales
├── astro.config.mjs      # Configuración de Astro
└── package.json
```

## 🖼️ Agregar Imágenes

1. Coloca tus imágenes en la carpeta `public/`
2. Actualiza las rutas en los componentes:
   - Foto de perfil
   - Imágenes de proyectos
   - Iconos personalizados

## 🚀 Despliegue

### Vercel (Recomendado)

```bash
npm install -g vercel
vercel
```

### Netlify

```bash
npm run build
# Sube la carpeta dist/
```

### GitHub Pages

Descomenta la configuración en `astro.config.mjs`:

```javascript
export default defineConfig({
  site: 'https://tu-usuario.github.io',
  base: '/tu-repo',
});
```

## 💡 Tips

1. **Imágenes Optimizadas**: Usa formato WebP o AVIF para mejor rendimiento
2. **CV Descargable**: Coloca tu CV en `public/cv.pdf`
3. **SEO**: Actualiza meta tags en `src/layouts/Layout.astro`
4. **Analytics**: Agrega Google Analytics o similar en el layout
5. **Performance**: Ejecuta Lighthouse para optimizaciones

## 🔗 Enlaces Útiles

- [Documentación de Astro](https://docs.astro.build)
- [Guía de despliegue](https://docs.astro.build/en/guides/deploy/)
- [Optimización de imágenes](https://docs.astro.build/en/guides/images/)

## 📝 Licencia

MIT - Siéntete libre de usar este template para tu propio portafolio

---

Desarrollado con ❤️ por Ivan Asdrubal Villegas Espinosa
