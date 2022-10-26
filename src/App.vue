<template>
  <router-view/>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500&display=swap');
/* font-family: 'Space Grotesk', sans-serif; */

*, *::before, *::after {
  box-sizing: border-box;
}
* {
  margin: 0;
}
html, body {
  height: 100%;
  font-family: 'Space Grotesk', sans-serif;
}
body {
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
  font-size: 18px;
}
img, picture, video, canvas, svg {
  display: block;
  max-width: 100%;
}
input, button, textarea, select {
  font: inherit;
}
p, h1, h2, h3, h4, h5, h6 {
  overflow-wrap: break-word;
}
#root, #__next {
  isolation: isolate;
}
:root{
  --white: hsl(0, 0%, 100%);
  --lightgreyviolet: hsl(270, 3%, 87%);
  --darkgreyviolet: hsl(279, 6%, 55%);
  --verydarkviolet: hsl(278, 68%, 11%);
}
</style>
