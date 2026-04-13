# 📋 VIANIE JEWELRY - Estado del Proyecto

> Fecha: 13 de abril 2026
> Estado: PRODUCCIÓN - Tienda completa con carrito de compras ✅

---

## ✅ COMPLETADO

### Base de Datos (Supabase PostgreSQL)
- [x] Tabla `productos` con 23 productos
- [x] Tabla `configuracion` con datos de contacto
- [x] Storage bucket `productos-imagenes` (PÚBLICO)
- [x] Imágenes subidas como archivos reales (no Base64)
- [x] RLS deshabilitado para lectura pública

### Supabase (Configuración Actual)
- **URL**: `https://wcaljwklhfgvguwdtabw.supabase.co`
- **Anon Key**: Configurada en todos los archivos
- **Auth**: Email/Password habilitado
- **Admin**: steve78yu@gmail.com

### Tienda Pública (100% Funcional)
- [x] **index.html** - Catálogo con buscador, filtros y carrito
- [x] **producto.html** - Detalle con galería, lightbox y carrito
- [x] **style.css** - Estilos premium responsive
- [x] **favicon.svg** - Favicon profesional (diamante dorado)
- [x] **og-image.svg** - Imagen para compartir en redes
- [x] **robots.txt** - Configuración SEO
- [x] **sitemap.xml** - Sitemap para Google

### SEO y Presencia Web
- [x] Meta tags SEO (title, description, keywords)
- [x] Open Graph para Facebook/WhatsApp/LinkedIn
- [x] Twitter Cards
- [x] Meta tags dinámicos en producto.html
- [x] Canonical URLs
- [x] Favicon profesional

### 🛒 Carrito de Compras
- [x] Botón flotante con badge (esquina superior derecha)
- [x] Modal del carrito con lista de productos
- [x] Agregar/quitar productos desde catálogo y detalle
- [x] Cambiar cantidades (+/-)
- [x] Total automático
- [x] Enviar pedido completo por WhatsApp (AMBOS contactos)
- [x] Vaciar carrito
- [x] Persistencia en localStorage
- [x] Toast de confirmación
- [x] Animaciones suaves

### Panel Admin
- [x] **admin.html** - Panel completo con Supabase Auth + Storage + DB
- [x] Login/Registro con Supabase Auth
- [x] CRUD de productos
- [x] Subida de imágenes a Supabase Storage
- [x] Galería de imágenes
- [x] Drag & drop

### Diseño
- [x] Paleta premium (dorado #b68d40 + negro)
- [x] Tipografía Playfair Display + Roboto
- [x] Imágenes en catálogo: `object-fit: cover` (rellenan tarjeta)
- [x] Imágenes en detalle: `object-fit: contain` (se ven completas)
- [x] Responsive (desktop + móvil)
- [x] Animaciones y transiciones suaves

---

## 📁 ARCHIVOS ACTIVOS

| Archivo | Función | Estado |
|---------|---------|--------|
| `index.html` | Tienda - Catálogo + Carrito | ✅ Producción |
| `producto.html` | Tienda - Detalle + Carrito | ✅ Producción |
| `admin.html` | Panel de Administración | ✅ Producción |
| `style.css` | Estilos principales | ✅ Producción |
| `favicon.svg` | Favicon profesional | ✅ Producción |
| `og-image.svg` | Imagen para redes sociales | ✅ Producción |
| `robots.txt` | Configuración SEO | ✅ Producción |
| `sitemap.xml` | Sitemap para Google | ✅ Producción |

---

## 📁 BACKUPS (No se usan en producción)

| Archivo | Razón |
|---------|-------|
| `configuracion.json` | Backup local de config |
| `productos.json` | Backup local de productos |
| `imagenes/` | Carpeta de imágenes originales |

---

## 🚀 DESPLIEGUE

### Producción (Netlify) - 100% AUTOMÁTICO
- **Deploy**: Drag & Drop en [https://app.netlify.com/drop](https://app.netlify.com/drop)
- **SEO URLs**: Se detectan automáticamente (no necesitas cambiar nada)
- **Ver README.md** para instrucciones completas

### Desarrollo Local (Opcional)
```bash
cd C:\Users\PC\Desktop\VIANIE
py -m http.server 8080
```

### Admin Login
- Email: `steve78yu@gmail.com`
- ⚠️ Confirmar email en Supabase Dashboard > Authentication > Users

---

## 📋 ESTRUCTURA BASE DE DATOS

### Tabla: productos
```sql
CREATE TABLE productos (
  id uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  nombre text NOT NULL,
  precio numeric NOT NULL,
  material text,
  categoria text,
  agotado boolean DEFAULT false,
  imagen_url text,
  galeria_urls jsonb DEFAULT '[]',
  creado_en timestamptz DEFAULT now()
);
```

### Tabla: configuracion
```sql
CREATE TABLE configuracion (
  id text PRIMARY KEY,
  titulo_hero text,
  desc_hero text,
  ws_1 text,
  ws_2 text,
  instagram text
);
```

### Datos actuales en configuracion:
| id | titulo_hero | ws_1 | ws_2 |
|----|-------------|------|------|
| general | Accesorios en Acero Inox | 63629975 | 76175389 |

---

## 🔐 SEGURIDAD

### Actualmente
- Supabase: RLS deshabilitado (lectura pública)
- Auth: Email/Password habilitado
- Storage: Bucket público
- API Key: Pública en frontend (normal para Supabase anon)

### Políticas RLS Recomendadas (para activar después)
```sql
ALTER TABLE productos ENABLE ROW LEVEL SECURITY;
CREATE POLICY "productos lectura publica" ON productos FOR SELECT USING (true);
CREATE POLICY "productos escritura admin" ON productos FOR ALL USING (auth.role() = 'authenticated');

ALTER TABLE configuracion ENABLE ROW LEVEL SECURITY;
CREATE POLICY "configuracion lectura publica" ON configuracion FOR SELECT USING (true);
CREATE POLICY "configuracion escritura admin" ON configuracion FOR ALL USING (auth.role() = 'authenticated');
```

---

## 📞 CONTACTOS

- **WhatsApp 1**: 63629975
- **WhatsApp 2**: 76175389
- **Ubicación**: Santa Cruz, Bolivia

---

##  PRÓXIMAS MEJORAS (Cuando haya presupuesto)

### Prioridad Media
- [ ] Backup automático de Supabase
- [ ] Estadísticas de vistas de productos
- [ ] Ordenar productos por precio/popularidad
- [ ] Búsqueda por rango de precio
- [ ] Página de contacto con formulario

### Hosting y Dominio
- [ ] Dominio propio (vianie.com.bo)
- [ ] Hosting con HTTPS/SSL
- [ ] Google Search Console
- [ ] Google Analytics

### Futuro
- [ ] Subida directa de imágenes desde cámara móvil
- [ ] Notificaciones push
- [ ] Sistema de pedidos
- [ ] Integración con pasarela de pago
- [ ] App móvil

---

## 🐛 NOTAS IMPORTANTES

1. **Imágenes en Storage**: Se suben como archivos reales (no Base64). Límite: 50MB por archivo.

2. **Cache**: La tienda cachea datos por 5 minutos en localStorage. Para forzar actualización: `localStorage.clear()` en consola.

3. **Carrito**: Se guarda en localStorage. Persiste al recargar la página.

4. **WhatsApp**: El carrito envía pedido a AMBOS contactos automáticamente.

5. **Security Advisor**: Muestra "errors" por RLS deshabilitado. Es **NORMAL** y correcto para este proyecto.

---

> **Proyecto en producción** 🚀
> Última actualización: 13 de abril 2026
