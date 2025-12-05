# 📱 UberEats Lite — Flutter App  
**Repositorio:** `ubereats-frontend`  
**Plataformas:** Android · iOS · Web · PWA  
**Consume:** API de `ubereaats-backend`

---

## 📌 Descripción General
Aplicación móvil y web desarrollada en **Flutter**, compatible con:

- 📱 Android  
- 🍎 iOS  
- 🌐 Web  
- 📲 PWA instalable (Add to Home Screen)

Características principales:
- Login con email/contraseña
- Login con Google / Apple (OAuth)
- Listado de restaurantes
- Menús y productos
- Carrito con TTL (Redis)
- Pedidos completos
- Tracking en tiempo real del repartidor
- App para cliente + vista para repartidor
- Mapa de ubicación (Google Maps / Flutter Map)

---

## 🚀 Tecnologías Usadas

| Área | Tecnología |
|------|------------|
| Framework | Flutter 3+ |
| Estado | Riverpod / Bloc |
| Almacenamiento seguro | flutter_secure_storage |
| Autenticación | google_sign_in · sign_in_with_apple |
| WebSockets | socket_io_client |
| Geolocalización | geolocator |
| Mapas | Google Maps / Flutter Map |
| PWA | service worker + manifest.json |

---

## 🧱 Estructura del Proyecto
/lib
/core
/features
/auth
/restaurants
/products
/cart
/orders
/delivery
/tracking
/widgets
main.dart

/web
manifest.json
icons/
flutter_service_worker.js

yaml
Copiar código

---

## 🔐 Autenticación
Incluye:

- Email / contraseña
- Sign in with Google
- Sign in with Apple
- Manejo seguro de Access/Refresh Tokens
- Auto-refresh de sesión via interceptor

Tokens se guardan en:

- **Secure Storage** (móvil)
- **Local Storage + cookies** (web/PWA)

---

## 🗺️ Tracking en Tiempo Real
Uso de `socket_io_client`:

- Cliente escucha `location:update`
- Renderiza la ruta del repartidor
- Mapa actualizado cada 5–10 segundos

---

## 🍕 Funcionalidades del Cliente
- Ver restaurantes
- Ver menú y productos
- Agregar al carrito
- Modificar cantidades
- Pagar (mock)
- Ver progreso del pedido
- Tracking en mapa
- Historial
- Perfil del usuario

---

## 🚴 Funcionalidades del Repartidor
- Ver pedidos asignados
- Aceptar / rechazar pedido
- Enviar ubicación al backend
- Ver destino en mapa
- Confirmar entrega

---

## 🌐 Funciones Web + PWA
Flutter Web genera:

- `/web/manifest.json`
- `/web/icons/`
- `/web/flutter_service_worker.js`

Funciones disponibles:

✔ Instalación como app  
✔ Splash screen  
✔ Modo standalone  
✔ Cache offline básico  
✔ Recarga automática cuando hay nueva versión  
✔ SEO básico  

---

## 🧪 Scripts Útiles

### Ejecutar en local
flutter run

shell
Copiar código

### Ejecutar versión web
flutter run -d chrome

shell
Copiar código

### Build web (PWA)
flutter build web

shell
Copiar código

### Build Android
flutter build apk

yaml
Copiar código

---

## 🔗 Conexión con Backend
Configurar la URL de la API en un archivo `.env`:

API_BASE_URL=https://<tu-api>.railway.app

yaml
Copiar código

Usa un cliente HTTP con interceptor que:

- Añade el Access Token
- Detecta expiración
- Llama automáticamente `/auth/refresh`

---

## 🏁 Estado del Proyecto
✔ Estructura inicial lista  
✔ Preparado para PWA  
✔ Integración completa con backend  

---

## 📄 Licencia
MIT — Libre para usar y modificar.