# Resumen del Laboratorio (ES)

Este laboratorio consistió en desplegar y proteger una aplicación web vulnerable usando herramientas open-source. El proceso incluyó:
- Despliegue de WebGoat en CentOS con Docker
- Escaneo con OWASP ZAP y Burp Suite
- Configuración de un proxy inverso con nginx en Debian
- Activación de ModSecurity con OWASP CRS 4.9.0
- Comparación de resultados antes y después del WAF
- Explotación de Spring4Shell usando Metasploit

Sin protección, la aplicación fue vulnerable a múltiples ataques (SQLi, XSS, Spring4Shell). Tras la implementación del WAF, muchos ataques fueron bloqueados, demostrando el refuerzo efectivo de seguridad con ModSecurity.
