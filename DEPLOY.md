# 🚀 Guía de Despliegue del Portafolio

## Preparación Antes del Deploy

### 1. Verificar que todo funciona localmente

```bash
# Instalar dependencias
npm install

# Modo desarrollo
npm run dev
# Visita http://localhost:4321

# Build de producción
npm run build

# Preview del build
npm run preview
```

### 2. Personalizar tu información

Antes de desplegar, **IMPORTANTE** actualizar:

✅ `src/components/HeroProfessional.astro`:
   - Tus datos personales
   - Enlaces sociales (GitHub, LinkedIn, Email)
   - Estadísticas reales

✅ `src/components/ProjectShowcase.astro`:
   - URLs de tus proyectos desplegados
   - Repositorios GitHub reales
   - Imágenes de proyectos (en `/public/`)
   - Descripciones técnicas

✅ `src/components/Experience.astro`:
   - Tu experiencia laboral real
   - Logros específicos
   - Educación actualizada

✅ `src/components/TechStack.astro`:
   - Tus niveles de habilidad reales
   - Certificaciones actualizadas

✅ `public/cv.pdf`:
   - Tu CV actualizado

## 🌐 Opción 1: Desplegar en Vercel (Recomendado)

### Por qué Vercel:
- ✅ Gratis para proyectos personales
- ✅ Deploy automático desde Git
- ✅ HTTPS automático
- ✅ CDN global
- ✅ Perfecto para Astro

### Pasos:

1. **Crear cuenta en Vercel**
   - Ve a [vercel.com](https://vercel.com)
   - Sign up con GitHub

2. **Push tu código a GitHub**
   ```bash
   git init
   git add .
   git commit -m "Portfolio profesional completo"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/portafolio.git
   git push -u origin main
   ```

3. **Importar proyecto en Vercel**
   - Click en "New Project"
   - Importar tu repositorio
   - Framework Preset: Astro
   - Click "Deploy"

4. **¡Listo!** Tu sitio estará en:
   `https://tu-proyecto.vercel.app`

### Configuración de dominio personalizado:
```
Settings → Domains → Add Domain
```

## 🟦 Opción 2: Desplegar en Netlify

### Pasos:

1. **Build tu proyecto**
   ```bash
   npm run build
   ```

2. **Crear cuenta en Netlify**
   - Ve a [netlify.com](https://netlify.com)

3. **Deploy desde Git**
   - Click "New site from Git"
   - Conecta con GitHub
   - Selecciona tu repositorio
   - Build command: `npm run build`
   - Publish directory: `dist`
   - Click "Deploy site"

O **deploy manual**:
```bash
# Instalar Netlify CLI
npm install -g netlify-cli

# Deploy
netlify deploy --prod --dir=dist
```

## 🐙 Opción 3: GitHub Pages

### Configurar:

1. **Actualizar `astro.config.mjs`**:
   ```javascript
   import { defineConfig } from 'astro/config';
   
   export default defineConfig({
     site: 'https://TU_USUARIO.github.io',
     base: '/portafolio',
   });
   ```

2. **Crear workflow de GitHub Actions**:
   
   Crear `.github/workflows/deploy.yml`:
   ```yaml
   name: Deploy to GitHub Pages

   on:
     push:
       branches: [ main ]
     workflow_dispatch:

   permissions:
     contents: read
     pages: write
     id-token: write

   jobs:
     build:
       runs-on: ubuntu-latest
       steps:
         - name: Checkout
           uses: actions/checkout@v3
         - name: Setup Node
           uses: actions/setup-node@v3
           with:
             node-version: '18'
         - name: Install dependencies
           run: npm ci
         - name: Build
           run: npm run build
         - name: Upload artifact
           uses: actions/upload-pages-artifact@v2
           with:
             path: ./dist

     deploy:
       environment:
         name: github-pages
         url: ${{ steps.deployment.outputs.page_url }}
       runs-on: ubuntu-latest
       needs: build
       steps:
         - name: Deploy to GitHub Pages
           id: deployment
           uses: actions/deploy-pages@v2
   ```

3. **Habilitar GitHub Pages**:
   - Ve a Settings → Pages
   - Source: GitHub Actions
   - Push tu código

Tu sitio estará en: `https://TU_USUARIO.github.io/portafolio`

## 🔧 Configuraciones Adicionales

### Variables de Entorno (si las necesitas):

**Vercel/Netlify**:
- Settings → Environment Variables
- Agregar tus variables

**Local**:
Crear `.env`:
```
PUBLIC_ANALYTICS_ID=tu-id
```

### Optimizaciones Pre-Deploy:

1. **Comprimir imágenes**:
   ```bash
   # Usa herramientas como:
   # - Squoosh.app
   # - TinyPNG
   # - ImageOptim
   ```

2. **Lighthouse Check**:
   - Abrir DevTools → Lighthouse
   - Ejecutar audit
   - Corregir issues

3. **Verificar Links**:
   - Todos los enlaces funcionan
   - URLs de proyectos activas
   - Links sociales correctos

## 🎯 Post-Deploy Checklist

- [ ] Verificar que todas las secciones cargan
- [ ] Probar responsive en móvil
- [ ] Verificar que links externos funcionan
- [ ] Comprobar velocidad de carga
- [ ] Probar en diferentes navegadores
- [ ] Verificar SEO básico
- [ ] Compartir en redes sociales
- [ ] Agregar a tu CV y LinkedIn

## 🌟 Tips Pro

### SEO
Actualizar `src/layouts/Layout.astro`:
```html
<meta name="description" content="Tu descripción">
<meta property="og:title" content="Tu nombre - Ingeniero">
<meta property="og:description" content="Tu descripción">
<meta property="og:image" content="/og-image.jpg">
<meta name="twitter:card" content="summary_large_image">
```

### Analytics
Agregar Google Analytics en `Layout.astro`:
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Dominio Personalizado

1. **Comprar dominio** (Namecheap, GoDaddy, etc.)
2. **Configurar DNS** según tu proveedor:
   - Vercel: Ver docs de Vercel
   - Netlify: Ver docs de Netlify
3. **Esperar propagación** (24-48 horas)

## 🆘 Troubleshooting

### Build falla:
```bash
# Limpiar cache
rm -rf node_modules dist .astro
npm install
npm run build
```

### Imágenes no cargan:
- Verificar rutas (relativas a `/public/`)
- Usar formato correcto (`/imagen.jpg` no `./imagen.jpg`)

### 404 en producción:
- Verificar `base` en `astro.config.mjs`
- Revisar rutas de navegación

## 📞 Soporte

- [Documentación Astro](https://docs.astro.build)
- [Discord de Astro](https://astro.build/chat)
- [Vercel Docs](https://vercel.com/docs)
- [Netlify Docs](https://docs.netlify.com)

---

¡Tu portafolio profesional está listo para el mundo! 🌍✨
