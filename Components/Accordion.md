# Snippet Reutilizable de Acordeón

Este snippet incluye el HTML, SCSS y JavaScript para un acordeón genérico y personalizable, ideal para FAQs, listas desplegables, o cualquier contenido colapsable.

## HTML

<!-- prettier-ignore -->
```html
<div class="accordion">
    <div class="accordion-item">
        <div class="accordion-header">
            <h4 class="accordion-title">Sección 1</h4>
            <img src="./assets/icons/arrow-down.svg" class="accordion-toggle" alt="Toggle" />
        </div>
        <div class="accordion-content">
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Doloremque, excepturi at. 
            Ducimus quam tempora, tempore culpa aliquid saepe, quae corrupti cupiditate nam, 
            quia quisquam cumque eaque minima voluptatibus dolorem aperiam.
        </div>
    </div>

    <div class="accordion-item">
        <div class="accordion-header">
            <h4 class="accordion-title">Sección 2</h4>
            <img src="./assets/icons/arrow-down.svg" class="accordion-toggle" alt="Toggle" />
        </div>
        <div class="accordion-content">
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Doloremque, excepturi at. 
            Ducimus quam tempora, tempore culpa aliquid saepe, quae corrupti cupiditate nam, 
            quia quisquam cumque eaque minima voluptatibus dolorem aperiam.
        </div>
    </div>

    <div class="accordion-item">
        <div class="accordion-header">
            <h4 class="accordion-title">Sección 3</h4>
            <img src="./assets/icons/arrow-down.svg" class="accordion-toggle" alt="Toggle" />
        </div>
        <div class="accordion-content">
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Doloremque, excepturi at. 
            Ducimus quam tempora, tempore culpa aliquid saepe, quae corrupti cupiditate nam, 
            quia quisquam cumque eaque minima voluptatibus dolorem aperiam.
        </div>
    </div>
</div>


/* Contenedor del Acordeón */
.accordion {
    padding: 1rem;
    width: 100%;
}

/* Elemento Individual del Acordeón */
.accordion-item {
    border: 2px solid #007bff; /* Color de borde personalizable */
    border-radius: 0.3rem;
    margin-bottom: 5px;
    background-color: #f9f9f9; /* Color de fondo personalizable */
}

/* Encabezado del Acordeón */
.accordion-header {
    display: flex;
    padding-inline: 1rem;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;

    .accordion-title {
        color: #007bff; /* Color del título personalizable */
        padding-block: 10px;
    }

    .accordion-toggle {
        width: 25px;
        height: 25px;
        transition: transform 0.3s ease; /* Transición suave para la rotación */

        &.turned {
            transform: rotate(180deg); /* Rotación al abrir */
        }
    }
}

/* Contenido del Acordeón */
.accordion-content {
    font-size: 1rem;
    padding-inline: 1rem;
    transition: all 0.3s ease-in-out; /* Transición suave para apertura/cierre */
    max-height: 0px;
    overflow: hidden;
    color: #333; /* Color del texto personalizable */

    &.active {
        max-height: 500px; /* Altura máxima al abrir, ajustable según contenido */
        padding-bottom: 1rem;
    }
}

// Selecciona todos los elementos del acordeón
const items = document.querySelectorAll(".accordion-item");

items.forEach((item) => {
    const header = item.querySelector(".accordion-header");

    header.addEventListener("click", () => {
        const content = item.querySelector(".accordion-content");
        const toggle = item.querySelector(".accordion-toggle");

        content.classList.toggle("active");
        toggle.classList.toggle("turned");
    });
});



