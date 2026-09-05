# E3 Pro Bluefy Reader — solo lectura

Web estática para iPhone + Bluefy. Implementa el mismo flujo Encryption2 ya validado en el diagnóstico de Windows:

- Nordic UART GATT
- PRE_COMM 0x5B
- AUTH 0x5D
- lectura MCU con Protocol 2
- drv_uid 0xDA (12 bytes)
- drv_rand 0xE4 (6 bytes)
- drv_flag 0xE7 (2 bytes)

## Seguridad

- No contiene comandos WRITE / WRITE_NR.
- No implementa flasheo/IAP.
- No contiene ninguna contraseña o serial incrustados.
- La credencial JSON se selecciona localmente y queda solo en memoria de la pestaña.
- No se realizan peticiones de red desde el JavaScript.

## Publicación gratuita con GitHub Pages

1. Crea un repositorio nuevo en GitHub, por ejemplo `e3-bluefy-reader`.
2. Sube `index.html` a la raíz del repositorio.
3. En GitHub: Settings → Pages.
4. Source: `Deploy from a branch`.
5. Branch: `main`, carpeta `/ (root)` y Save.
6. Espera a que GitHub muestre la URL HTTPS.
7. En el iPhone instala Bluefy y abre ESA URL dentro de Bluefy.
8. Selecciona tu archivo `credencial_ninebot_*.json` desde Archivos.
9. Pulsa Conectar → selecciona el E3 Pro → Autenticar → Leer drv_uid.

Safari normal de iOS no sirve para Web Bluetooth; la URL debe abrirse dentro de Bluefy.
