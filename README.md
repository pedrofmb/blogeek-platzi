# Blogeek Videos
Proyecto de referencia para el curso en Platzi de Firebase para la Web. 
- Recuerda crear un directorio config y dentro un archivo javascript con nombre ConfigFirebase el cual contiene las credenciales y demas info para usar firebase.
- Existen ramas por clase, sin embargo en la rama master esta la versión final
- Mira la versión final: https://blogeekplatzi.firebaseapp.com/

@jggomezt

***Reglas bd firestone para que solo pued insertar o eliminar si el usuario esta logeado

match /posts/{post}/{uid} {
        allow update, delete: if request.auth.uid == uid
                && request.resource.data.email == resource.data.email
}

***Reglas para el storage

match /imgPosts/{userId}/{imgId} {
        allow write: if request.resource.size < 5 * 1024 * 1024
                && request.resource.contentType.matches('image/.*')
                && request.auth.uid != null
                && request.auth.uid == userId
}