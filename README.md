ValidadorIdentificacion
=============================


Introducción
-------------

Básicamente la Clase ValidadorIdentificacion permitirá tener una clase para validar Cédula y RUC del Ecuador. Se busca llegar a 
los lenguajes más populares: php, js, java, .net (vb, c-sharp), ruby.

Ya la clase inicial creada en php permite validar CI y RUC de persona natural. Proximamente se agregará funcionalidad
para validar RUC de personas jurídicas y empresas del estado Ecuatoriano.

El siguiente link permitira conocer un poco más de la matematica asociada:

http://www.icaiza.com/blog/programacion/como-validar-el-digito-verificador-de-la-cedula-ecuatoriana

Adjuntamos también un documento teórico (This is an [instructivo.pdf](https://github.com/diaspar/validacion-cedula-ruc-ecuador/blob/master/instructivo.pdf) - página 36 a la 40)


Uso
----

- Incluir la clase en el proyecto PHP deseado.
- Instanciar la clase y llamar al metodo para validar CI o RUC de persona natural

```
// Crear nuevo objecto
$validador = new ValidarIdentificacion();

// validar CI
if ($validador->validarCedula('0926687856')) {
    echo 'Cédula válida';
} else {
    echo 'Cédula incorrecta: '.$validador->getMessage();
}

// validar RUC persona natural
if ($validador->validarRucPersonaNatural('0926687856001')) {
    echo 'RUC válido';
} else {
    echo 'RUC incorrecto: '.$validador->getMessage();
}
```


Tests
-------

Para ver todos los mensajes de error que provee la clase se adjunta archivo de tests.

Para poder correr los tests, instalar y usar phpunit de la siguiente forma:

phpunit --verbose  --colors ValidarIdentificacionTest.php 
