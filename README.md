# K&S International Legal Assistance
## Sitio Web Profesional para Katherine Chica Mejía

---

## Descripción

Sitio web profesional y moderno para servicios legales especializados en derecho migratorio y penal. Diseñado con colores corporativos del logo (azul marino, rojo y dorado) para proyectar confianza y profesionalismo.

---

## Características

- ✅ Diseño 100% responsive (móvil, tablet, PC)
- ✅ Animaciones suaves y profesionales
- ✅ Formulario de contacto funcional
- ✅ SEO optimizado
- ✅ Carga rápida
- ✅ Navegación intuitiva
- ✅ Secciones: Inicio, Servicios, Sobre Mí, Contacto

---

## Estructura de Archivos

```
ks-legal/
│
├── index.html          # Página principal
├── styles.css          # Estilos personalizados
├── script.js           # JavaScript para interactividad
├── logo.png            # Logo de K&S (AGREGAR ESTE ARCHIVO)
└── README.md           # Este archivo
```

---

## Instalación y Uso

### Opción 1: Abrir directamente en el navegador (Más fácil)

1. Guarda tu logo como `logo.png` en la carpeta `ks-legal`
2. Haz doble clic en `index.html`
3. El sitio se abrirá en tu navegador predeterminado

### Opción 2: Usar un servidor local (Recomendado para desarrollo)

**Con Visual Studio Code:**
1. Instala la extensión "Live Server"
2. Click derecho en `index.html` → "Open with Live Server"

**Con Python:**
```bash
cd ks-legal
python -m http.server 8000
# Abre http://localhost:8000 en tu navegador
```

**Con Node.js:**
```bash
npx http-server ks-legal
```

---

## Personalización

### 1. Agregar Logo
- Guarda tu logo como `logo.png` en la carpeta principal
- Recomendación: imagen PNG con fondo transparente, 500x500px mínimo

### 2. Agregar Foto Profesional
En `index.html`, línea ~165, reemplaza:
```html
<div class="image-placeholder">
```
Con:
```html
<img src="tu-foto.jpg" alt="Katherine Chica Mejía" style="width: 100%; border-radius: 10px;">
```

### 3. Actualizar Información de Contacto

**Email y Teléfono:**
Edita en `index.html` (líneas ~355-375):
```html
<p><a href="mailto:TU_EMAIL@ejemplo.com">TU_EMAIL@ejemplo.com</a></p>
<p><a href="tel:+57XXXXXXXXXX">+57 XXX XXX XXXX</a></p>
```

**Redes Sociales:**
Edita en `index.html` (líneas ~390-420):
```html
<a href="https://wa.me/573XXXXXXXXX" class="social-link">WhatsApp</a>
<a href="https://linkedin.com/in/TU_PERFIL" class="social-link">LinkedIn</a>
<a href="https://instagram.com/TU_PERFIL" class="social-link">Instagram</a>
```

### 4. Modificar Contenido

- **Servicios:** Líneas 220-330 en `index.html`
- **Sobre Mí:** Líneas 150-210 en `index.html`
- **Colores:** Variables CSS en `styles.css` líneas 8-16

---

## Integración de Formulario de Contacto

El formulario actualmente muestra un mensaje de éxito simulado. Para hacerlo funcional:

### Opción A: EmailJS (Recomendado - Sin backend)

1. Crea cuenta en [EmailJS.com](https://www.emailjs.com)
2. Configura un servicio de email
3. Crea una plantilla de email
4. Agrega antes de `</head>` en `index.html`:

```html
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
<script>
    emailjs.init('TU_PUBLIC_KEY');
</script>
```

5. En `script.js`, reemplaza la función `simulateFormSubmission` con:

```javascript
function submitForm(data) {
    return emailjs.send('TU_SERVICE_ID', 'TU_TEMPLATE_ID', {
        from_name: data.name,
        from_email: data.email,
        phone: data.phone,
        subject: data.subject,
        message: data.message
    });
}
```

### Opción B: Formspree (Muy fácil)

1. Crea cuenta en [Formspree.io](https://formspree.io)
2. Reemplaza el `<form>` en `index.html`:

```html
<form action="https://formspree.io/f/TU_FORM_ID" method="POST" class="contact-form">
```

### Opción C: Backend Personalizado (PHP)

Crea `contact.php`:

```php
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = $_POST['name'];
    $email = $_POST['email'];
    $message = $_POST['message'];

    $to = "tu-email@ejemplo.com";
    $subject = "Nueva consulta desde web";
    $body = "Nombre: $name\nEmail: $email\n\nMensaje:\n$message";

    mail($to, $subject, $body);

    echo json_encode(["status" => "success"]);
}
?>
```

---

## Hosting y Publicación

### Opciones Gratuitas:

**1. GitHub Pages (Recomendado)**
```bash
# 1. Crea repositorio en GitHub
# 2. Sube los archivos
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/TU_USUARIO/ks-legal.git
git push -u origin main

# 3. Activa GitHub Pages en Settings → Pages
# Tu sitio estará en: https://TU_USUARIO.github.io/ks-legal/
```

**2. Netlify**
- Arrastra la carpeta `ks-legal` a [netlify.com/drop](https://app.netlify.com/drop)
- Obtienes un sitio en minutos

**3. Vercel**
- Conecta tu repositorio de GitHub
- Deploy automático

### Opciones de Pago (Con dominio personalizado):

- **Hostinger** - Desde $2/mes
- **Namecheap** - Desde $3/mes
- **GoDaddy** - Desde $5/mes
- **Colombian Hosting** - Desde COP $10,000/mes

---

## Dominio Personalizado

Para tener un dominio tipo `www.kslegal.com.co`:

1. **Compra un dominio** (.com.co recomendado para Colombia)
   - Namecheap.com
   - GoDaddy.com
   - Hosting.com.co

2. **Conecta con tu hosting:**
   - GitHub Pages: Configurar CNAME
   - Netlify/Vercel: Agregar dominio en configuración

---

## Mejoras Futuras Recomendadas

- [ ] Sistema de citas online
- [ ] Blog de artículos legales
- [ ] Chat en vivo (WhatsApp Business)
- [ ] Versión en inglés
- [ ] Calculadora de costos de visa
- [ ] Portal de clientes (área privada)
- [ ] Testimonios de clientes
- [ ] Casos de éxito

---

## SEO - Optimización para Google

### Archivos adicionales a crear:

**robots.txt:**
```
User-agent: *
Allow: /
Sitemap: https://tu-dominio.com/sitemap.xml
```

**sitemap.xml:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://tu-dominio.com/</loc>
    <lastmod>2024-01-01</lastmod>
    <priority>1.0</priority>
  </url>
</urlset>
```

### Google My Business:
1. Crea perfil en [google.com/business](https://www.google.com/business/)
2. Verifica tu ubicación en El Poblado
3. Agrega fotos, horarios, servicios

---

## Soporte Técnico

Para modificaciones o soporte:
- Revisa los comentarios en el código
- Todas las secciones están claramente marcadas
- Usa Visual Studio Code para editar fácilmente

---

## Checklist de Lanzamiento

Antes de publicar:

- [ ] Agregar logo (logo.png)
- [ ] Agregar foto profesional
- [ ] Actualizar email de contacto
- [ ] Actualizar número de teléfono
- [ ] Configurar formulario de contacto (EmailJS/Formspree)
- [ ] Actualizar enlaces de redes sociales
- [ ] Revisar todos los textos
- [ ] Probar en móvil, tablet y PC
- [ ] Configurar Google Analytics (opcional)
- [ ] Comprar dominio
- [ ] Configurar hosting
- [ ] Crear cuentas de redes sociales profesionales

---

## Tecnologías Utilizadas

- HTML5
- CSS3 (Grid, Flexbox, Animations)
- JavaScript (Vanilla)
- Google Fonts (Playfair Display, Poppins)
- Font Awesome Icons (via SVG)

---

## Licencia

Sitio web creado exclusivamente para K&S International Legal Assistance - Katherine Chica Mejía.

---

## Contacto del Desarrollador

Si necesitas modificaciones o ayuda adicional, el código está completamente documentado para facilitar cambios futuros.

---

**¡Éxito con tu nueva página web! 🎉**