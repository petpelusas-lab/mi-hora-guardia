# Mi Hora Guardia — export desde Lovable

Este repositorio contendrá el proyecto exportado desde Lovable (React + Vite + TypeScript) y archivos de CI para compilar la web y generar artefactos nativos.

Instrucciones rápidas:
1. Exporta/importe los archivos desde Lovable (si no lo has hecho aún). Si no puedes descargar el ZIP, conecta la exportación a este repositorio desde Lovable.
2. Desde la raíz del repo:
   - npm install
   - npm run build

Conversión a app nativa (opciones):
- Móvil: usar Capacitor (recomendado para portar la app web a Android/iOS).
- Escritorio: usar Tauri (recomendado por tamaño y seguridad).

CI:
- Incluye workflows para construir la web (Vite) y un ejemplo para generar AAB de Android vía Capacitor.
- Para firmar el AAB en CI, añade los secretos en GitHub (ver README abajo).

Secrets necesarios (si usas el workflow Android AAB):
- ANDROID_KEYSTORE (keystore en base64)
- ANDROID_KEYSTORE_PASSWORD
- ANDROID_KEY_ALIAS
- ANDROID_KEY_PASSWORD

Pasos para Android via Capacitor (resumen):
1. npm install @capacitor/core @capacitor/cli
2. npx cap init "AppName" "com.tu.dominio.app"
3. npm run build
4. npx cap add android
5. npx cap copy
6. Abrir `android/` en Android Studio para generar signed bundle o usar el workflow CI incluido.

Cuando todo esté listo, responde “listo” en este chat y procederé a añadir más archivos/PRs si quieres.
