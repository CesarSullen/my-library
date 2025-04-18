- {
  margin: 0;
  padding: 0;
  outline: none;
  box-sizing: border-box;
  border: none;
  transition: all 0.3s;
  list-style: none;
  text-decoration: none;
  font-family: "Poppins";
  }

// Variables
$primary-color: #19150f;
$secondary-color: #c8c5ba;
$text-color: #333;
$border-radius-general: 8px;
$border-general: solid 1px rgba($primary-color, 0.4);

// Typography
@font-face {
font-family: "MeowScript";
src: url("../typography/MeowScript-Regular.ttf") format("truetype");
font-weight: 400;
}
@font-face {
font-family: "Poppins";
src: url("../typography/Poppins-Regular.ttf") format("truetype");
font-weight: 400;
}

// Utilities
.important-text {
color: $primary-color;
}
.bold {
font-weight: 600;
}
.italic {
font-style: italic;
}
.underline {
text-decoration: underline;
}
.hidden {
opacity: 0;
scale: 0.8;
}
.shown {
opacity: 1;
scale: 1;
}
hr {
width: 100%;
background-color: $secondary-color;
height: 2px;
}
body {
background-color: $secondary-color;
}
.body-content {
padding: 1rem;
max-width: 1200px;
margin: auto;
display: grid;
grid-template-columns: 1fr;
color: black;
gap: 50px;
}
a {
color: $primary-color;
}
.btn {
padding: 0.8rem 1.6rem;
border-radius: $border-radius-general;
border: solid 2px $primary-color;
background: $primary-color;
font-size: 1rem;
cursor: pointer;
width: 100%;
min-width: 200px;
letter-spacing: 2px;
text-transform: uppercase;
color: $secondary-color;
text-align: center;
font-weight: 600;
position: relative;
overflow: hidden;
transition: all 0.3s ease;

    &:active {
    	transform: scale(0.95);
    	box-shadow: none;
    }

    &:after {
    	content: "";
    	position: absolute;
    	top: 50%;
    	left: 50%;
    	width: 0;
    	height: 0;
    	background: rgba($secondary-color, 0.2);
    	border-radius: 50%;
    	transform: translate(-50%, -50%);
    	transition: width 0.4s ease, height 0.4s ease;
    }

    &:hover:after {
    	width: 300px;
    	height: 300px;
    	pointer-events: none;
    }
    &:hover {
    	translate: 0px -5px;
    }

}

.ghost-btn {
background: transparent;
border: solid 2px $primary-color;
color: $primary-color;
transition: all 0.3s ease;

    &:hover {
    	background: $primary-color;
    	color: $secondary-color;
    	box-shadow: 0 4px 12px rgba($primary-color, 0.3);
    	transform: translateY(-2px);
    }

    &:active {
    	transform: scale(0.95);
    	box-shadow: none;
    }

}
section {
text-align: center;

    h2 {
    	margin-bottom: 30px;
    }

}
.card {
border-radius: $border-radius-general;
	box-shadow: 0 4px 20px rgba($primary-color, 0.3);
background: rgba(245, 245, 245, 0.5);
overflow: hidden;
border: $border-general;
.card-content {
position: relative;
padding: 1rem;
gap: 10px;
display: flex;
flex-direction: column;
}

    &::after {
    	content: "✿";
    	position: absolute;
    	bottom: 0;
    	right: 10px;
    	font-size: 8rem;
    	color: rgba($primary-color, 0.1);
    	pointer-events: none;
    	line-height: 1;
    	transform: translateY(25%);
    	z-index: -1;
    	opacity: 0;
    	transition: opacity 0.3s ease;
    }

    &:hover {
    	transform: translateY(-5px);
    	box-shadow: 0 4px 20px rgba($primary-color, 0.8);
    }

    &:hover::before,
    &:hover::after {
    	opacity: 1;
    }

}
