// Reset
* {
  margin: 0;
  padding: 0;
  outline: none;
  box-sizing: border-box;
  border: none;
  transition: all 0.2s;
  list-style: none;
  text-decoration: none;
  outline: none;
}

// Typography
@font-face {
  font-family: "*name*";
  src: url("../typography/") format("truetype");
  font-weight: 400;
}

// Colors
$bg-color: ;
$primary-color: ;
$font-color: ;

// Utilities
.important-text {
  color: $primary-color;
}
.bold {
  font-weight: 600;
}
.italic{
  font-style: italic;
}
.underline {
  text-decoration: underline;
}
.body-container {
  padding: 1.5rem;
  max-width: 1000px;
  margin: auto;
}
.btn {
  padding: 1rem 2rem;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;
  width: 100%;
  max-width: 400px;
  background-color: $primary-color;
  color: $bg-color;

  &:hover {
    box-shadow: 0 0 10px 1px $primary-color;
  }
  &:active {
    transform: scale(0.9);
  }
}
.warning-text {
  color: red;
}
