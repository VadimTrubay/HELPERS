# BASE STYLES

:root {
--brand-color: #044D29;
--secondary-brand-color: #ECF6F1;
--link: #044D29;
--link-hover: #A1D697;
--main-background-color: #ffffff;
--secondary-background-color: #ECF6F1;
}

/* Reset base styles */
*,
*::before,
*::after {
box-sizing: border-box;
margin: 0;
padding: 0;
}

html,
body {
height: 100%;
margin: 0;
padding: 0;
font-family: Nunito Sans, sans-serif;
line-height: 1.6;
}

h1,
h2,
h3,
h4,
h5,
h6,
p {
margin: 0;
padding: 0;
font-weight: normal;
}

ul,
ol {
margin: 0;
padding: 0;
list-style: none;
}

a {
color: inherit;
text-decoration: none;
}

img {
display: block;
max-width: 100%;
height: auto;
}

/* Common utility classes */
.container {
max-width: 900px;
min-height: 550px;
margin: 0 auto;
padding: 0;
box-shadow: 0 0 10px;
border-radius: 10px;
border-left: solid 1px #c5c5c5;
border-right: solid 1px #c5c5c5;
}

.text-center {
text-align: center;
}

.hidden {
display: none !important;
}


