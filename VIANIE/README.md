# 💎 VIANIE JEWELRY

> Tienda online de accesorios en acero inoxidable

**URL en producción**: [AQUÍ_IRÁ_LA_URL_DE_NETLIFY](#)

---

## 📦 Tecnologías

- **Frontend**: HTML5 + CSS3 + JavaScript vanilla
- **Base de datos**: Supabase PostgreSQL
- **Auth**: Supabase Auth
- **Storage**: Supabase Storage
- **Hosting**: Netlify
- **CDN**: Supabase JS Client (desde CDN)

---

## 🚀 Despliegue en Netlify

### Opción 1: Drag & Drop (Más fácil)

1. Ve a [https://app.netlify.com/drop](https://app.netlify.com/drop)
2. Arrastra la **carpeta completa** `VIANIE` al área de drop
3. Espera a que se despliegue (30 segundos)
4. ¡Listo! Tu sitio estará en `https://tu-sitio.netlify.app`

### Opción 2: Conectando a Git (Recomendado)

1. Crea un repositorio en GitHub
2. Sube todos los archivos de esta carpeta
3. En Netlify: **Add new site** > **Import an existing project**
4. Selecciona GitHub y conecta tu repositorio
5. Configuración automática:
   - **Publish directory**: `.`
   - **Build command**: (vacío)
   - **Deploy branch**: `main`
6. Click en **Deploy site**

### Opción 3: CLI de Netlify

```bash
# Instalar CLI
npm install -g netlify-cli

# Login
netlify login

# Deploy
netlify deploy --prod
```

---

## ⚙️ Configuración Post-Despliegue

### 1. Dominio personalizado
En Netlify > Site settings > Domain management > Add custom domain

### 2. HTTPS
Netlify proporciona HTTPS automáticamente (Let's Encrypt)

### 3. Formularios (opcional)
Si agregas un formulario de contacto, agrega el atributo `netlify` al `<form>`

### 4. Variables de entorno (si las necesitas)
En Netlify > Site settings > Environment variables

---

## 📁 Estructura del Proyecto

```
VIANIE/
├── index.html          # Página principal (catálogo)
├── producto.html       # Detalle de producto
├── admin.html          # Panel de administración
├── style.css           # Estilos principales
├── favicon.svg         # Favicon
├── og-image.svg        # Imagen para redes sociales
├── robots.txt          # SEO - Permitir indexar
├── sitemap.xml         # SEO - Sitemap
├── _redirects          # Netlify redirects
├── netlify.toml        # Configuración Netlify
├── .gitignore          # Git ignore
├── README.md           # Este archivo
└── imagenes/           # Imágenes originales (no se suben)
```

---

## 🗄️ Supabase

### Configuración
- **URL**: `https://wcaljwklhfgvguwdtabw.supabase.co`
- **Tablas**: `productos`, `configuracion`
- **Storage**: `productos-imagenes` (bucket público)

### Credenciales Admin
- **Email**: `steve78yu@gmail.com`
- **Nota**: Confirmar email en Supabase Dashboard > Authentication > Users

---

## 🛒 Carrito de Compras

- Productos se guardan en `localStorage`
- Envía pedido por WhatsApp a AMBOS contactos
- Persistente al recargar la página

---

## 📞 Contactos

- **WhatsApp 1**: 63629975
- **WhatsApp 2**: 76175389
- **Ubicación**: Santa Cruz, Bolivia

---

## 📝 Notas Importantes

1. **No usar `file://`**: Siempre servir con un servidor local para desarrollo
2. **Cache**: La tienda cachea datos por 5 minutos. Limpiar con `localStorage.clear()`
3. **Imágenes**: Se suben a Supabase Storage (no al repositorio)
4. **Admin**: Protegido con Supabase Auth

---

> **Última actualización**: 13 de abril 2026
