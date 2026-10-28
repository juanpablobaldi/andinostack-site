# andinostack.com

Sitio de **Andino Stack LLC** (Nuevo México). Página estática, sin dependencias: `index.html`, `privacy.html`,
`404.html`, `styles.css` y `favicon.svg`. Sirve para la verificación de organización de Apple, Google Play y
Dun & Bradstreet (D-U-N-S): sitio público en el dominio de la empresa y mail de contacto en ese dominio.

Ver en local:

```bash
python3 -m http.server 5055
```

## Publicar (GitHub Pages + Cloudflare, igual que antesydespues.app)

1. Repo público en GitHub con estos archivos → Settings → Pages → Source: `main` / root.
2. Custom domain: `andinostack.com` (ya está el archivo `CNAME`). Después de que el DNS resuelva, activar
   **Enforce HTTPS**.
3. DNS en Cloudflare, con la nube **gris** (DNS only; si no, GitHub no puede emitir el certificado):
   - `A` `@` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` `www` → `juanpablobaldi.github.io`
4. Mail: Cloudflare → Email → **Email Routing** → activar (crea los registros MX solo) → direcciones
   `contact@andinostack.com` y `juanpablo@andinostack.com` (o "catch-all") que reenvían al Gmail.
