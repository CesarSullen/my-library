// CSS

.fade-in {
  transform: translateY(100px);
  opacity: 0;
  transition: 0.5s;

  &.show {
    transform: translateY(0);
    opacity: 1;
  }
}

// JS

const sections = document.querySelectorAll(".fade-in");

const observer = new IntersectionObserver(
  (entries) => {
    entries.forEach((entry) => {
      entry.target.classList.toggle("show", entry.isIntersecting);
      if (entry.isIntersecting) {
        observer.unobserve(entry.target);
      }
    });
  },
  {
    threshold: 0.1,
  }
);
sections.forEach((section) => {
  observer.observe(section);
});
