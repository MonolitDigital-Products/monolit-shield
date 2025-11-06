# 🛡️ Monolit Shield (Hardened) — MU Plugin para Desarrolladores
**Endurecimiento automático de WordPress (versión Must-Use)**  
Pensado para agencias y desarrolladores que buscan seguridad por defecto sin paneles, menús ni opciones.

> Desarrollado y mantenido por **[Monolit Digital](https://monolit.digital)**

## 🚀 Características principales
- **Alias del área de administración** → `/admin-portal` por defecto (personalizable)
- **Bloqueo de enumeración de usuarios** → `?author=1` y `/wp-json/wp/v2/users`
- **Desactiva XML-RPC, feeds y pingbacks**
- **Limpieza del `<head>`** → quita generator, oEmbed y discovery
- **Ofuscación de emails** en HTML y JSON-LD
- **Cabeceras de seguridad**: X-Content-Type-Options, X-Frame-Options, Referrer-Policy, Permissions-Policy y CSP (*Report-Only*)
- Compatible con Elementor y WPML
- Cero configuración. Comportamiento determinista.

## ⚙️ Instalación (MU)
Copia el contenido de `mu-plugins/` a `wp-content/mu-plugins/`.

Recomendado: aplica las plantillas de `server/` (Apache / Nginx).

### Cambiar el alias
En `wp-config.php`:
```php
define( 'MSHIELD_ADMIN_SLUG', 'your-custom-admin-slug' );
```
Después accede a: `https://tudominio.com/your-custom-admin-slug/`

## 🔍 Verificaciones rápidas
```bash
curl -I https://tudominio.com/wp-admin/             # → 403 (anónimo)
curl -I https://tudominio.com/admin-portal/         # → login
curl -I https://tudominio.com/wp-json/wp/v2/users   # → 403
curl -I https://tudominio.com/xmlrpc.php            # → 403
```

## 🧱 Compatibilidad
- WordPress 5.8 → 6.8+
- PHP 7.4 → 8.3+
- Funciona con cachés/CDNs/hostings administrados
- **No** edita `.htaccess` automáticamente (incluye plantillas)

## 🛠️ Desarrollo
- Licencia: MIT
- Sin telemetría, sin interfaz
- PRs bienvenidos — ver <a href="./CONTRIBUTING.md">CONTRIBUTING.md</a>

## 🧾 Cambios
Ver <a href="./CHANGELOG.md">CHANGELOG.md</a>

---

© 2025 Monolit Digital — https://monolit.digital
