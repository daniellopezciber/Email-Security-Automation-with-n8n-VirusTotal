# 🛡️ Email Security Automation with n8n + VirusTotal

Este proyecto es un **flujo automatizado en n8n** que analiza correos electrónicos entrantes, extrae enlaces y los verifica en **VirusTotal** para detectar posibles amenazas. En caso de encontrar un enlace malicioso, el sistema envía una **alerta de seguridad automática** al usuario.

---

## 🚀 Características

* Lectura automática de correos entrantes (Gmail en este ejemplo).
* Extracción de todos los enlaces contenidos en los correos.
* Análisis de cada enlace mediante la API de **VirusTotal**.
* Evaluación automática de amenazas en base al informe recibido.
* Envío de **alertas de seguridad** por correo si se detecta algún enlace malicioso.
* Flujo **modular y escalable**, adaptable a otros proveedores de correo o servicios de seguridad.

---

## 📌 Flujo en n8n



1. **Despertador diario** → Activa el flujo automáticamente una vez al día.
2. **Leer nuevos correos** → Obtiene los correos no leídos de la bandeja.
3. **Procesar correo por lotes** → Divide la lista de correos para analizarlos individualmente.
4. **Extraer enlaces (JavaScript)** → Detecta y extrae todas las URLs presentes en el contenido.
5. **Enviar a VirusTotal** → Llama a la API de VirusTotal para iniciar el análisis.
6. **Esperar (30s)** → Da tiempo a que VirusTotal complete el análisis.
7. **Obtener informe final** → Recupera el resultado completo de VirusTotal.
8. **¿Es peligroso?** → Verifica si la URL fue catalogada como maliciosa.
9. **Enviar alerta de seguridad** → Si es malicioso, se envía un correo con la advertencia.

---

## 🛠️ Requisitos

* [n8n](https://n8n.io) instalado (local o en servidor).
* Cuenta de Gmail o cualquier servicio IMAP/SMTP.
* Clave API de [VirusTotal](https://www.virustotal.com/gui/join-us).

---

## ⚙️ Configuración

1. Importa el archivo `detector amenazas gmail.json` en tu instancia de n8n.

2. Configura las credenciales:

   * **Gmail API** (o tu servicio de correo).
   * **VirusTotal API Key**.

3. Ajusta los parámetros de búsqueda (ej: últimos 24h, correos no leídos).
4. Activa el flujo y revisa las ejecuciones.

---



## 📢 Notas

* Este flujo es **educativo y demostrativo**. No reemplaza soluciones profesionales de ciberseguridad.
* Puedes ampliarlo añadiendo integraciones con **Slack, Teams, Telegram o SIEMs**.

---

## 👨‍💻 Autor

Proyecto creado por Daniel Lopez https://github.com/daniellopezciber. ✨

Si te gusta este proyecto, ¡no olvides dejar una ⭐ en el repo! 🚀

