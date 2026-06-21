# SCRAPER DataStore — Guía rápida

## 1. Instalar dependencias (una sola vez)
```
npm install
```
Demora 3-5 minutos. Descarga Puppeteer (Chromium).

## 2. Crear archivo .env
Copia .env.example como .env y reemplaza:
- API_URL: ya está apuntando a tu Hostinger
- API_TOKEN: pega el token de tu scraper_config.php en Hostinger

## 3. Probar conexión al endpoint
```
node test-connection.js
```
Si sale "OK 200" estás conectado bien.

## 4. Correr el scraper

Para un proveedor específico:
```
npm run scrape:caleta
npm run scrape:pcmaster
```

Para todos:
```
npm run scrape:all
```

## 5. Workflow de GitHub Actions
Para que se ejecute automáticamente, sube TODO menos el .env a tu repo.
Configura los secrets API_URL y API_TOKEN en Settings → Secrets.

## Estructura
- scraper.js: motor principal
- run-all-scrapers.js: ejecuta todos los proveedores
- config/suppliers.js: configuración de PCMaster y Caleta
- config/categories.js: mapeo de categorías
- .github/workflows/scraper.yml: workflow automático

## Tabla en BD donde llega
- catalogo_proveedor: productos sincronizados
- scraper_logs: historial de cada corrida
