// HTML

<div class="accordion">
        <div class="accordion-item section">
          <div class="accordion-header">
            <h4 class="accordion-title">Pregunta 1</h4>
            <img src="images/icons/arrow-down.svg" class="accordion-toggle" />
          </div>
          <div class="accordion-content">
            Lorem ipsum dolor sit amet consectetur, adipisicing elit.
            Doloremque, excepturi at. Ducimus quam tempora, tempore culpa
            aliquid saepe, quae corrupti cupiditate nam, quia quisquam cumque
            eaque minima voluptatibus dolorem aperiam.
          </div>
        </div>

        <div class="accordion-item section">
          <div class="accordion-header">
            <h4 class="accordion-title">Pregunta 2</h4>
            <img src="images/icons/arrow-down.svg" class="accordion-toggle" />
          </div>
          <div class="accordion-content">
            Lorem ipsum dolor sit amet consectetur, adipisicing elit.
            Doloremque, excepturi at. Ducimus quam tempora, tempore culpa
            aliquid saepe, quae corrupti cupiditate nam, quia quisquam cumque
            eaque minima voluptatibus dolorem aperiam.
          </div>
        </div>

        <div class="accordion-item section">
          <div class="accordion-header">
            <h4 class="accordion-title">Pregunta 3</h4>
            <img src="images/icons/arrow-down.svg" class="accordion-toggle" />
          </div>
          <div class="accordion-content">
            Lorem ipsum dolor sit amet consectetur, adipisicing elit.
            Doloremque, excepturi at. Ducimus quam tempora, tempore culpa
            aliquid saepe, quae corrupti cupiditate nam, quia quisquam cumque
            eaque minima voluptatibus dolorem aperiam.
          </div>
        </div>

        <div class="accordion-item section">
          <div class="accordion-header">
            <h4 class="accordion-title">Pregunta 4</h4>
            <img src="images/icons/arrow-down.svg" class="accordion-toggle" />
          </div>
          <div class="accordion-content">
            Lorem ipsum dolor sit amet consectetur, adipisicing elit.
            Doloremque, excepturi at. Ducimus quam tempora, tempore culpa
            aliquid saepe, quae corrupti cupiditate nam, quia quisquam cumque
            eaque minima voluptatibus dolorem aperiam.
          </div>
        </div>

        // CSS
        .accordion {
padding: 1rem;
width: 100%;
}
.accordion-item {
border: 2px solid $primary-color;
border-radius: 0.3rem;
margin-bottom: 5px;
background-color: $background;
}
.accordion-header {
display: flex;
padding-inline: 1rem;
justify-content: space-between;
align-items: center;
cursor: pointer;

.accordion-title {
color: $primary-color;
padding-block: 10px;
}
.accordion-toggle {
width: 25px;
height: 25px;

    &.turned {
      transform: rotate(180deg);
    }

}
}
.accordion-content {
font-size: 1rem;
padding-inline: 1rem;
transition: all 0.3s ease-in-out;
max-height: 0px;
overflow: hidden;
color: #fff;

&.active {
max-height: 500px;
padding-bottom: 1rem;
}
}

// JS
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
