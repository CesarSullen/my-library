# Snippet Reutilizable de Carrusel

Este snippet incluye el HTML, SCSS y JavaScript para un carrusel de imágenes simple con navegación manual y automática, personalizable para cualquier proyecto.

## HTML

<!-- prettier-ignore -->
```html
<div class="carousel">
    <div class="carousel-images">
        <a href="#" target="_blank">
            <img src="./assets/images/slide1.jpg" alt="Slide 1" />
        </a>
        <a href="#" target="_blank">
            <img src="./assets/images/slide2.jpg" alt="Slide 2" />
        </a>
        <a href="#" target="_blank">
            <img src="./assets/images/slide3.jpg" alt="Slide 3" />
        </a>
    </div>
    <button id="prevBtn">Anterior</button>
    <button id="nextBtn">Siguiente</button>
</div>

/* Contenedor del Carrusel */
.carousel {
    position: relative;
    max-width: 600px; /* Ancho máximo personalizable */
    margin: auto;
    width: 100%;
}

/* Contenedor de Imágenes */
.carousel-images {
    display: flex;
    overflow: hidden;
    border-radius: 10px 10px 10px 10px; /* Radio de borde personalizable */
}

/* Estilo de las Imágenes */
.carousel-images img {
    width: 100%;
    display: none;
}

/* Imagen Activa */
.carousel-images img.active {
    display: block;
}

/* Estilo de los Botones */
button {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: none;
    padding: 5px 5px;
    border: none;
    border-radius: 100vh; /* Forma circular, personals personalizable */
    cursor: pointer;

    img {
        width: 50px; /* Tamaño de ícono personalizable, si usas imágenes en botones */
}

/* Posición del Botón Anterior */
#prevBtn {
    left: 10px; /* Posición personalizable */
}

/* Posición del Botón Siguiente */
#nextBtn {
    right: 10px; /* Posición personalizable */
}

// Selecciona todas las imágenes del carrusel
const images = document.querySelectorAll(".carousel-images img");
let currentImage = 0;

// Muestra la imagen actual
function showImage(index) {
    images.forEach((img) => img.classList.remove("active"));
    images[index].classList.add("active");
}

// Avanza a la siguiente imagen
function nextImage() {
    currentImage = (currentImage + 1) % images.length;
    showImage(currentImage);
}

// Retrocede a la imagen anterior
function prevImage() {
    currentImage = (currentImage - 1 + images.length) % images.length;
    showImage(currentImage);
}

// Event listeners para los botones
document.getElementById("prevBtn").addEventListener("click", prevImage);
document.getElementById("nextBtn").addEventListener("click", nextImage);

// Muestra la primera imagen al cargar
showImage(currentImage);

// Temporizador para cambio automático
let timer = setInterval(nextImage, 5000);

// Reinicia el temporizador al interactuar con los botones
document.querySelectorAll("#prevBtn, #nextBtn").forEach((btn) => {
    btn.addEventListener("click", () => {
        clearInterval(timer);
        timer = setInterval(nextImage, 5000);
    });
});
