# Fichas de Farmacología

Aplicación web de tarjetas de estudio creada con React y Tailwind CSS. Los datos se almacenan en **Firebase Firestore**, lo que permite compartir y actualizar la información en tiempo real. Está pensada para ser servida como sitio estático (por ejemplo con GitHub Pages).

## Configuración de Firebase
1. Crea un proyecto en [Firebase Console](https://console.firebase.google.com/) y habilita **Firestore** en modo producción.
2. En la sección de configuración del proyecto, obtén el objeto de credenciales (apiKey, authDomain, etc.).
3. Sustituye los valores de `firebaseConfig` en `index.html` con los de tu proyecto.
4. Ajusta las reglas de seguridad de Firestore según tus necesidades.

Al cargar la aplicación por primera vez, si la colección `drugs` está vacía se insertarán automáticamente algunas fichas de ejemplo.

## Despliegue en GitHub Pages
1. Haz un fork o sube este repositorio a GitHub.
2. En la configuración del repositorio, activa **GitHub Pages** apuntando a la rama principal (`main`/`master`) en la carpeta raíz.
3. Tras unos minutos tendrás una URL pública del estilo `https://usuario.github.io/repositorio/`.

Cada vez que hagas cambios y los subas, GitHub Pages regenerará el sitio. Los datos guardados en Firestore permanecerán.

## Desarrollo local
Puedes abrir `index.html` directamente en tu navegador. Si tu navegador bloquea las dependencias externas en modo archivo, sirve la carpeta con un servidor sencillo:

```bash
python -m http.server 8000
```

Luego visita [http://localhost:8000](http://localhost:8000).

Las preferencias de tema y colores se guardan en `localStorage` por navegador, mientras que las fichas se sincronizan a través de Firestore.
