# cortes-enre

# 🕵️‍♂️ Scraper de incidentes en la página del ENRE (Edenor & Edesur)

Este proyecto realiza un raspado de datos (**scraping**) automático y periódico de la página oficial del **ENRE** (Ente Nacional Regulador de la Electricidad) para obtener el estado del servicio eléctrico y las fallas en las redes de **Edenor** y **Edesur** en tiempo real.

La recolección de datos está totalmente automatizada mediante **GitHub Actions**, ejecutándose de forma continua para mantener un historial actualizado.

---

## 🚀 Características

* **Scraping Automatizado:** Extrae la cantidad de usuarios afectados, fallas en el servicio técnico y cortes preventivos.
* **Automatización con GitHub Actions:** El script se ejecuta automáticamente **cada 2 horas**.
* **Persistencia de Datos:** Los datos extraídos se guardan automáticamente en el repositorio generando un historial con cada ejecución.
* **Liviano y Eficiente:** Desarrollado en Python para ejecutarse en contenedores sin consumir recursos excesivos.

---

## 🛠️ Tecnologías Utilizadas

* **Lenguaje:** Python
* **Automatización:** GitHub Actions (Cron Workflow)
* **Librerías principales:** BeautifulSoup4 / Requests / Pandas

---

## 📅 Automatización (GitHub Actions)

El archivo de configuración en `.github/workflows/scraper.yml` utiliza una tarea programada (*cron job*) para correr el script cada dos horas:

```yaml
on:
  schedule:
    - cron: '0 */2 * * *' # Se ejecuta cada 2 horas en punto
