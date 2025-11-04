# Seguridad en la Aplicación

Este documento resume las mejores prácticas de seguridad implementadas en esta aplicación, incluyendo autenticación, almacenamiento de tokens y protección contra ataques comunes.


---

## 🛡 Recomendaciones de implementación

1. **Tokens**

   * **Access token:** corta duración (ej. 15 minutos), guardado **solo en memoria**.
   * **Refresh token:** larga duración (ej. 1 día), guardado en **cookie HttpOnly, SameSite=Strict**.

2. **Autenticación**

   * Usar JWT con firma RSA (RS256) para prevenir falsificación de tokens.
   * Implementar fingerprint para detectar cambios de dispositivo o IP y reforzar seguridad.

3. **Protección frontend**

   * Evitar `innerHTML` sin sanitizar y validar todos los inputs de usuario.
   * Aplicar **Content Security Policy (CSP)** para controlar scripts y recursos externos.
   * Usar **CAPTCHA** en formularios públicos para evitar ataques automatizados.

4. **Protección backend**

   * Usar HTTPS obligatorio en producción.
   * Aplicar **CSRF protection** si se usan cookies para refresh tokens.
   * Configurar **rate limiting** y logging para prevenir abusos.
   * Validar CAPTCHA antes de procesar formularios públicos.

5. **Recomendaciones adicionales**

   * Revisar periódicamente vulnerabilidades con herramientas como `npm audit`, Snyk o OWASP ZAP.
   * Validar tokens y fingerprint en cada request.
   * Expirar tokens robados o sospechosos inmediatamente.

---

## ⚡ Flujo recomendado

1. El usuario inicia sesión mediante el proveedor de autenticación.
2. El backend valida la autenticación y genera:

   * **Access token** (guardado en memoria)
   * **Refresh token** (guardado en cookie HttpOnly)
3. El frontend utiliza el access token para llamadas API **(no en localStorage ni en cookies accesibles por JS)**.
4. Cuando expira el access token, se solicita un nuevo token usando el refresh token en cookie HttpOnly.
5. Todas las requests protegidas validan **fingerprint**, JWT y CSRF (si aplica).
6. Formularios públicos pasan validación CAPTCHA.
7. CSP y buenas prácticas de frontend previenen XSS.

---

> Este esquema asegura un equilibrio entre **usabilidad y seguridad**, protegiendo la app contra CSRF, XSS, falsificación de tokens y accesos no autorizados.

---

## 🔒 Conceptos clave de seguridad

* **Fingerprint:** Evita que otro dispositivo use credenciales robadas mediante un hash único del dispositivo, navegador o IP.
* **RSA (firma de JWT):** Garantiza que los tokens no puedan ser falsificados, incluso si se conoce el secreto.
* **OIDC (OpenID Connect):** Protocolo estandarizado para autenticación segura con proveedores externos.
* **PKCE:** Protege el código de autorización en SPAs o apps móviles, evitando que un atacante reutilice el `auth code`.
* **MFA (Multi-Factor Authentication):** Requiere un segundo factor de autenticación, aumentando la seguridad ante robo de credenciales.
* **Seguridad del guardado del token:** Access token en memoria; Refresh token en cookie HttpOnly con SameSite=Strict.
* **CSRF (Cross-Site Request Forgery):** Protege contra peticiones maliciosas utilizando cookies.
* **XSS (Cross-Site Scripting):** Previene que scripts maliciosos roben tokens o manipulen la UI.
* **CSP (Content Security Policy):** Limita orígenes de scripts y recursos para prevenir ejecución de código malicioso.
* **CAPTCHA:** Evita que bots automatizados envíen formularios públicos, reduciendo spam y ataques de fuerza bruta.
