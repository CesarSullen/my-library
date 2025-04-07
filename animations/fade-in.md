# Snippet Reutilizable de Animación Fade-In

Este snippet incluye el HTML (ejemplo), SCSS y JavaScript para una animación de aparición (fade-in) al hacer scroll, activada cuando los elementos entran en el viewport.

## HTML

<!-- prettier-ignore -->
```html
<!-- Ejemplo de uso: aplica la clase "fade-in" a cualquier elemento -->
<section class="fade-in">
    <h2>Sección 1</h2>
    <p>Contenido que aparece con animación al hacer scroll.</p>
</section>

<section class="fade-in">
    <h2>Sección 2</h2>
    <p>Más contenido que se revela con el efecto fade-in.</p>
</section>

<div class="fade-in">
    <img src="./assets/images/example.jpg" alt="Imagen con animación" />
</div>

/* Estilo para elementos con animación fade-in */
.fade-in {
    transform: translateY(100px); /* Posición inicial, personalizable */
    opacity: 0; /* Opacidad inicial */
    transition: 0.5s; /* Duración y tipo de transición, personalizable */

    /* Estado visible */
    &.show {
        transform: translateY(0); /* Posición final */
        opacity: 1; /* Opacidad final */
    }
}

// Selecciona todos los elementos con la clase fade-in
const sections = document.querySelectorAll(".fade-in");

// Configura el observador de intersección
const observer = new IntersectionObserver(
    (entries) => {
        entries.forEach((entry) => {
            entry.target.classList.toggle("show", entry.isIntersecting);
            if (entry.isIntersecting) {
                observer.unobserve(entry.target); /* Deja de observar una vez visible */
            }
        });
    },
    {
        threshold: 0.1, /* Porcentaje de visibilidad para activar, personalizable */
    }
);

// Observa cada elemento
sections.forEach((section) => {
    observer.observe(section);
});
