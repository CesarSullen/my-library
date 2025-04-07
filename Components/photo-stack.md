# Snippet Reutilizable de Pila de Fotos

Este snippet incluye el HTML y SCSS para una galería de fotos apiladas, diseñada para ser reutilizable en cualquier contexto.

## HTML

<!-- prettier-ignore -->
```html
<div class="photo-stack">
    <img src="./assets/gallery/photo1.jpg" class="photo-stack-item" alt="Foto 1" />
    <img src="./assets/gallery/photo2.jpg" class="photo-stack-item" alt="Foto 2" />
    <img src="./assets/gallery/photo3.jpg" class="photo-stack-item" alt="Foto 3" />
</div>

/* Contenedor de la Pila de Fotos */
.photo-stack {
    width: 100%;
    max-width: 600px; /* Ancho máximo personalizable */
    position: relative;
}

/* Estilo de Fotos Individuales */
.photo-stack-item {
    width: 100%;
    border: 8px solid white; /* Color de borde personalizable */
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2); /* Sombra personalizable */
    aspect-ratio: 4/5; /* Mantiene las proporciones de la foto */
    object-fit: cover;
    object-position: top;
    position: relative;
    transition: transform 0.3s ease, box-shadow 0.3s ease; /* Transición suave al hover */

    /* Transformaciones para apilar */
    &:first-child {
        transform: rotate(-25deg) translateX(-20%);
        z-index: 1;
    }

    &:nth-child(2) {
        transform: rotate(5deg) translate(5%, -10%);
        z-index: 2;
    }

    &:last-child {
        transform: rotate(-10deg) translate(-12%, -25%);
        z-index: 1;
    }

    /* Efecto al pasar el ratón */
    &:hover {
        transform: rotate(0deg) scale(1.2); /* Restaura rotación y aumenta escala */
        box-shadow: 0 5px 10px rgba(0, 0, 0, 0.4); /* Sombra más intensa */
        z-index: 3;
    }

    /* Ajustes responsivos */
    @media screen and (min-width: 700px) {
        max-width: 200px; /* Ancho máximo personalizable para pantallas grandes */
    }
}
