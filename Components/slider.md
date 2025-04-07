# Snippet Reutilizable de Sliders

Este snippet incluye el HTML y SCSS para dos sliders (normal y en reversa) con variables personalizables.

## HTML

<!-- prettier-ignore -->
```html
<!-- Slider Normal -->
<div class="slider" style="--width: 150px; --height: 150px; --quantity: 10">
    <div class="list">
        <!-- Repite los ítems según sea necesario -->
        <div class="item" style="--position: 1">
            <img src="./assets/images/image1.jpg" alt="Slide 1" />
        </div>
        <div class="item" style="--position: 2">
            <img src="./assets/images/image2.jpg" alt="Slide 2" />
        </div>
        <!-- Añade más ítems con --position incrementado -->
    </div>
</div>

<!-- Slider en Reversa -->
<div class="slider" reverse="true" style="--width: 200px; --height: 200px; --quantity: 9">
    <div class="list">
        <!-- Repite los ítems según sea necesario -->
        <div class="item" style="--position: 1">
            <img src="./assets/images/image3.jpg" alt="Slide 1" />
        </div>
        <div class="item" style="--position: 2">
            <img src="./assets/images/image4.jpg" alt="Slide 2" />
        </div>
        <!-- Añade más ítems con --position incrementado -->
    </div>
</div>

/* Contenedor del Slider */
.slider {
    width: 100%;
    height: var(--height); /* Altura personalizable vía variable CSS */
    overflow: hidden;
    mask-image: linear-gradient(to right, transparent, #000 10% 90%, transparent);

    /* Variante en reversa */
    &[reverse="true"] {
        .item {
            animation: reversePlay 10s linear infinite; /* Animación en reversa */
        }
    }

    /* Efectos al pasar el ratón */
    &:hover {
        .item {
            animation-play-state: paused !important;
            filter: grayscale(1); /* Escala de grises al hover, personalizable */
        }
    }
}

/* Lista del Slider */
.list {
    display: flex;
    width: 100%;
    min-width: calc(var(--width) * var(--quantity)); /* Ancho dinámico según ítems */
    position: relative;
}

/* Ítem del Slider */
.item {
    width: var(--width); /* Ancho personalizable vía variable CSS */
    height: var(--height); /* Coincide con la altura del slider */
    position: absolute;
    left: 100%;
    animation: autoRun 10s linear infinite; /* Animación por defecto */
    animation-delay: calc(
        (10s / var(--quantity)) * (var(--position) - 1)
    ) !important; /* Retraso dinámico según posición */

    img {
        width: 100%;
        height: 100%;
        object-fit: cover; /* Asegura que las imágenes encajen bien */
    }

    &:hover {
        filter: grayscale(0) !important; /* Anula escala de grises al hover individual */
    }
}

/* Animación para dirección normal */
@keyframes autoRun {
    from {
        left: 100%;
    }
    to {
        left: calc(var(--width) * -1);
    }
}

/* Animación para dirección en reversa */
@keyframes reversePlay {
    from {
        left: calc(var(--width) * -1);
    }
    to {
        left: 100%;
    }
}
