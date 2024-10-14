// HTML

<div class="carousel">
          <div class="carousel-images">
            <a
              href="#" tarjet="_blank"
            >
              <img src="" alt="Anuncio 1" />
            </a>

            <a href="#" target="_blank">
              <img src="" alt="Anuncio 2" />
            </a>

            <a href="#" target="_blank">
              <img src="" alt="Anuncio 3" />
            </a>
          </div>
          <button id="prevBtn">Anterior</button>
          <button id="nextBtn">Siguiente</button>
        </div>

// CSS

.carousel {
  position: relative;
  max-width: 600px;
  margin: auto;
  width: 100%;
}

.carousel-images {
  display: flex;
  overflow: hidden;
  border-radius: 10px 10px 10px 10px;
}

.carousel-images img {
  width: 100%;
  display: none;
}

.carousel-images img.active {
  display: block;
}

button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background:none;
  padding: 5px 5px;
  border: none;
  border-radius: 100vh;
  cursor: pointer;

  img {
    width: 50px;
  }
}

#prevBtn {
  left: 10px;
}

#nextBtn {
  right: 10px;
}

// JS

const images = document.querySelectorAll(".carousel-images img");
let currentImage = 0;

function showImage(index) {
  images.forEach((img) => img.classList.remove("active"));
  images[index].classList.add("active");
}

function nextImage() {
  currentImage = (currentImage + 1) % images.length;
  showImage(currentImage);
}

function prevImage() {
  currentImage = (currentImage - 1 + images.length) % images.length;
  showImage(currentImage);
}

document.getElementById("prevBtn").addEventListener("click", prevImage);

document.getElementById("nextBtn").addEventListener("click", nextImage);

showImage(currentImage);

let timer = setInterval(nextImage, 5000);

document.querySelectorAll("#prevBtn, #nextBtn").forEach((btn) => {
  btn.addEventListener("click", () => {
    clearInterval(timer);
    timer = setInterval(nextImage, 5000);
  });
});

