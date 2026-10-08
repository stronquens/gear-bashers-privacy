# Política de privacidad de Gear Bashers

Última actualización: 8 de octubre de 2026.

Esta política describe Gear Bashers, paquete Android `com.stronquensstudio.gearbashers`, desarrollado por **Stronquens Studio**. Contacto para privacidad y soporte: **stronquens@gmail.com**.

## Alcance de esta versión

La alpha actual se distribuye mediante invitaciones privadas. Incluye partidas locales con bots, multijugador online y conexiones entre dispositivos. No incluye anuncios ni compras dentro del juego. No solicita una cuenta de correo, contraseña o acceso con Google o Apple para jugar.

Para solicitar la eliminación de datos, consulta [Conservación y solicitudes](https://stronquens.github.io/gear-bashers-privacy/#conservacion-y-solicitudes).

## Datos almacenados en el móvil

El juego guarda preferencias como idioma, audio, gráficos, controles y configuración de partidas. Los modos multijugador también utilizan un alias elegido por el jugador. Estos ajustes pueden eliminarse borrando los datos de la aplicación desde Android. Esto no elimina por sí solo los datos de los servicios online.

## Partidas online

Al utilizar las funciones online se inicializan servicios de **Unity Gaming Services**:

- **Authentication** genera un identificador de jugador y credenciales de sesión anónima. «Anónima» significa que no se pide una cuenta personal al jugador; sigue existiendo un identificador persistente del servicio.
- **Relay** procesa el identificador y la dirección IP para conectar la partida. Su documentación declara también ubicación aproximada, actividad y rendimiento del servicio, utilizados para funcionamiento y análisis técnico.
- **Lobby** publica y mantiene los anuncios de salas públicas. El nombre de sala, alias de anfitrión y participantes, personajes, plazas, versión y configuración de sala pueden ser visibles para otros usuarios que consulten el listado. Las salas privadas no se anuncian en ese directorio, pero sus participantes reciben la información necesaria para jugar.

Estos datos sirven para identificar sesiones, descubrir salas y sincronizar partidas. No introduzcas nombres completos, direcciones, teléfonos u otros datos personales en alias o nombres de sala. Comparte los códigos privados únicamente con las personas con las que quieras jugar.

Las comunicaciones con Unity usan conexiones cifradas; el transporte Relay del juego utiliza DTLS. Unity y sus proveedores procesan datos necesarios para esos servicios. Consulta la [política de privacidad para jugadores de Unity](https://unity.com/legal/game-player-and-app-user-privacy-policy).

## Red local y dispositivos cercanos

En red local, los dispositivos intercambian direcciones de red, alias, información de sala y estado de partida. El transporte LAN del prototipo no añade cifrado propio: úsalo en una red de confianza.

En Android, el modo Cercanos utiliza **Google Play services Nearby Connections**, con Bluetooth y Wi-Fi. Pide los permisos correspondientes al entrar en ese modo; en Android 12 y anteriores puede requerir permiso de ubicación para descubrir dispositivos. El código del juego no utiliza coordenadas GPS para ubicar al jugador. Puedes denegar o revocar estos permisos; las partidas locales con bots siguen disponibles.

Nearby cifra las conexiones entre participantes. Google documenta la recopilación de métricas de conexión y datos técnicos —modelo de dispositivo, país, versión del sistema y paquete de aplicación— según la configuración de uso y diagnóstico de Google del móvil. Puedes controlar esa recopilación desde **Ajustes → Google → Uso y diagnóstico**. Consulta la [documentación de Nearby Connections](https://developers.google.com/nearby/connections/overview) y la [política de privacidad de Google](https://policies.google.com/privacy).

## Estadísticas y diagnóstico voluntarios

Las versiones que muestran **Datos y diagnóstico** ofrecen dos opciones inicialmente
desactivadas. Puedes cambiarlas desde Opciones, también durante una partida. Denegarlas
no impide jugar. Utilizamos **Google Firebase Analytics y Crashlytics**:

- **Estadísticas de juego:** navegación por menús, selección de personajes/mapas,
  configuración y resultados de partidas, goles, bloqueos y usos de poderes. Analytics
  utiliza identificadores de instalación y procesa datos técnicos del móvil, ubicación
  aproximada inferida por Google a partir de la conexión y actividad
  de la aplicación. No añadimos tu alias, correo ni códigos de sala a estos eventos.
- **Errores y rendimiento:** fallos, información técnica de excepción/pila nativa,
  versión del juego/sistema/dispositivo, memoria, tiempos de frames y contexto de red.
  La medición de batería es aproximada y corresponde al dispositivo completo. Los errores
  estructurados del juego se agrupan mediante una huella de pila, sin copiar su mensaje
  ni el texto de los registros. El SDK puede incluir información técnica de un fallo nativo.
- Los informes comparativos de rendimiento de Analytics requieren ambas opciones.
  Con solo diagnóstico, el último resumen se adjunta como contexto a informes de fallo.

No grabamos pantallas, vídeo de partidas ni todas las pulsaciones. No se configura
publicidad personalizada ni un identificador publicitario. Firebase/Google procesa
los datos consentidos para analizar el juego y diagnosticar fallos; sus comunicaciones
utilizan TLS. Consulta la [privacidad y seguridad de Firebase](https://firebase.google.com/support/privacy).

Al revocar una opción se descartan sus eventos pendientes en memoria y se detiene
su envío futuro. Crashlytics tiene el envío automático desactivado: los informes
se conservan temporalmente en el dispositivo y solo se envían en un arranque posterior
si proceden de una ejecución consentida y el diagnóstico sigue aceptado. Se descartan
informes de ejecuciones sin consentimiento o revocadas. Una activación a mitad de
ejecución comienza a ser elegible para esos informes en el siguiente arranque.
Revocar el consentimiento no elimina automáticamente datos ya recibidos por Google.

## Soporte y distribución

Si escribes al correo de soporte, recibimos tu dirección y la información que envíes para atender la consulta. Evita enviar contraseñas, códigos de autenticación o información personal innecesaria. Google Play gestiona la distribución y la participación en pruebas conforme a sus propias condiciones y política de privacidad.

## Conservación y solicitudes

Las preferencias locales permanecen hasta que las borres. Authentication mantiene el identificador hasta su eliminación mediante las herramientas del proveedor; Unity indica una conservación de 30 días para datos personales de Relay. Los anuncios de salas se actualizan, cierran o caducan según la sesión y el servicio. No se promete que desinstalar el juego borre datos remotos.

Google documenta una conservación de 90 días para pilas de fallo e identificadores
asociados de Crashlytics antes de iniciar su eliminación de sistemas activos y copias.
Los datos de Analytics se conservan según sus controles de retención; los informes
agregados pueden tener una conservación diferente. No utilizamos estos datos para
publicidad ni los exportamos a un almacén propio.

Puedes solicitar información, acceso, rectificación o eliminación escribiendo a **stronquens@gmail.com** con el asunto «Privacidad Gear Bashers». Indica la versión y el contexto necesario para localizar tu sesión; acordaremos una comprobación proporcional sin pedir tu contraseña. La alpha todavía no ofrece un botón de eliminación de identidad online dentro del juego. Las solicitudes que afecten a Unity o Google se gestionan mediante sus herramientas o soporte, según el servicio. Como no vinculamos la telemetría con tu correo o alias, esos datos por sí solos pueden no permitir localizar una instalación.

## Menores

Esta versión se dirige a personas de **13 años en adelante**. No está dirigida a menores de 13 años. El juego todavía no incorpora un control de edad ni consentimiento parental verificado para los servicios online. La futura incorporación de jugadores menores de 13 años, incluido el multijugador, requiere adaptar esos servicios y revisar esta política antes de distribuirles el juego.

Si un padre, madre o tutor cree que se han tratado datos de un menor de forma inadecuada, puede contactar con **stronquens@gmail.com** para revisar el caso y tramitar las medidas correspondientes.

## Cambios

Actualizaremos esta política cuando cambien las funciones o los servicios utilizados. La fecha de esta página identifica la versión vigente.
