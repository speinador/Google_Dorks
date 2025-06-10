# 🕵️‍♂️ Google Dorks y Google Hacking - Tutorial Completo

Este repositorio contiene un tutorial completo sobre **Google Dorks**, su uso en técnicas de **OSINT (Open Source Intelligence)**, y su aplicación en auditorías de seguridad y **hacking ético**.

---

## 📌 ¿Qué son los Google Dorks?

Los Google Dorks son consultas avanzadas que utilizan operadores especiales en el motor de búsqueda de Google para acceder a información específica, que a menudo no aparece con búsquedas comunes.

👉 Se utilizan ampliamente en **ciberseguridad**, **pentesting**, **OSINT**, **reconocimiento previo a un ataque** y **auditorías web**. A través de operadores especiales, permiten encontrar archivos confidenciales, cámaras abiertas, paneles de login, información sensible expuesta y mucho más.

---

## 🧠 Operadores de búsqueda avanzados (Google Dorks)

A continuación, una lista completa de operadores dorks que se pueden combinar para obtener resultados más precisos:

| Operador         | Descripción                                                   | Ejemplo                                     |
|------------------|---------------------------------------------------------------|---------------------------------------------|
| `site:`          | Restringe la búsqueda a un dominio específico                 | `site:gov.ar`                               |
| `inurl:`         | Busca coincidencias en la URL                                | `inurl:admin`                               |
| `intitle:`       | Busca coincidencias en el título de la página                | `intitle:"index of"`                        |
| `allintitle:`    | Todas las palabras deben aparecer en el título               | `allintitle: login panel`                   |
| `intext:`        | Busca coincidencias en el texto visible de la página         | `intext:"confidential"`                    |
| `allintext:`     | Todas las palabras deben aparecer en el cuerpo de la página  | `allintext: password username`              |
| `filetype:`      | Busca archivos de un tipo específico                          | `filetype:pdf`                              |
| `ext:`           | Igual que `filetype`, permite buscar por extensión           | `ext:docx`                                  |
| `cache:`         | Muestra la versión en caché de una página                    | `cache:example.com`                         |
| `link:`          | Muestra páginas que enlazan al sitio indicado                | `link:example.com`                          |
| `related:`       | Muestra páginas similares a la indicada                      | `related:example.com`                       |
| `define:`        | Muestra la definición de una palabra                         | `define:phishing`                           |
| `info:`          | Información general sobre una URL                            | `info:example.com`                          |
| `*`              | Comodín que reemplaza cualquier palabra                      | `intitle:"index of" *.mp4`                 |
| `OR`             | Permite hacer consultas múltiples                            | `login OR admin`                            |
| `AND`            | Une dos condiciones obligatorias                             | `filetype:xls AND site:edu`                 |
| `-`              | Excluye un término                                            | `site:example.com -blog`                    |
| `"palabra"`      | Busca la frase exacta entre comillas                         | `"confidential report"`                    |

---

## 🛠️ Técnicas útiles con ejemplos

### 1. Formularios de login
```bash
inurl:login site:edu.ar
```

### 2. Directorios expuestos
```bash
intitle:"index of" "backup"
```

### 3. Cámaras IP accesibles
```bash
inurl:"/view.shtml"
```

### 4. Archivos con contraseñas
```bash
filetype:txt intext:"password" site:.com
```

### 5. Documentos confidenciales en instituciones públicas
```bash
site:gov.ar filetype:pdf "confidencial"
```

### 6. Bases de datos SQL filtradas por extensión
```bash
filetype:sql site:.edu
```

### 7. Archivos Excel con datos personales
```bash
filetype:xls intext:"dni" OR intext:"documento" site:org.ar
```

### 8. Paneles de administración
```bash
intitle:"admin panel" OR inurl:admin
```

### 9. Documentos de configuración del servidor
```bash
filetype:env OR filetype:conf OR filetype:ini "DB_PASSWORD"
```

### 10. Historial de navegación filtrado
```bash
filetype:log intext:"GET /index.html" site:.com
```

---

## 🧪 Casos de uso educativos y prácticos

- Reconocimiento previo en pentesting (recon)
- Recolección de inteligencia OSINT en investigaciones abiertas
- Auditorías internas de seguridad
- Demostraciones de vulnerabilidades en capacitaciones
- Verificación de exposición accidental de archivos o datos sensibles

---

## ⚖️ Consideraciones legales

⚠️ Este contenido es estrictamente educativo.  
El uso indebido de Google Dorks para acceder a información privada sin autorización puede ser **ilegal**.

- ✅ Permitido: Usos educativos, investigaciones propias, pruebas en entornos controlados.
- ❌ No permitido: Acceder o explotar datos personales o privados sin consentimiento explícito.

Recordá siempre tener autorización previa para realizar cualquier tipo de prueba de seguridad sobre sistemas de terceros.

---

## 📚 Recursos adicionales

- 🔗 [Google Hacking Database (GHDB)](https://www.exploit-db.com/google-hacking-database/)
- 📘 *Google Hacking for Penetration Testers* - Johnny Long
- 🧰 Herramientas OSINT: Shodan, Maltego, FOCA, Recon-ng
- 🛠️ Alternativas y combinaciones útiles con Google:
  - `site:linkedin.com/in` para recolección de perfiles laborales
  - `site:pastebin.com` para encontrar filtraciones
  - `inurl:wp-admin` para buscar WordPress vulnerables

---

## 🧑‍🏫 Autor

Explicación elaborada por [Sebastian Peinador](https://www.linkedin.com/in/sebastian-j-peinador/) para propósitos didácticos y de investigación en ciberseguridad ofensiva.

---

## 📄 Licencia

Este material se distribuye bajo la licencia [MIT](LICENSE).

---

> Si te resulta útil, ¡no olvides darle ⭐ al repo o compartirlo!
