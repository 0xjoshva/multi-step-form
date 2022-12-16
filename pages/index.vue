<template>
  <main>
    <h1>hello this is the homepage</h1>
  </main>
</template>

<script setup></script>

<style lang="scss" scoped>
//CSS Reset
*,
*::before,
*::after {
  box-sizing: border-box;
}
* {
  margin: 0;
}
html,
body {
  height: 100%;
}
body {
  line-height: 1.5;
  -webkit-font-smoothing: antialiased;
}
img,
picture,
video,
canvas,
svg {
  display: block;
  max-width: 100%;
}
input,
button,
textarea,
select {
  font: inherit;
}
p,
h1,
h2,
h3,
h4,
h5,
h6 {
  overflow-wrap: break-word;
}
#root,
#__next {
  isolation: isolate;
}

//Font
@import url("https://fonts.googleapis.com/css2?family=Ubuntu:wght@300;400;500;700&display=swap");
$myFont: "Ubuntu", sans-serif;

//Primary
$marineBlue: hsl(213, 96%, 18%);
$purplishBlue: hsl(243, 100%, 62%);
$pastelBlue: hsl(228, 100%, 84%);
$lightBlue: hsl(206, 94%, 87%);
$strawberryRed: hsl(354, 84%, 57%);

//Secondary
$coolGray: hsl(231, 11%, 63%);
$lightGray: hsl(229, 24%, 87%);
$magnolia: hsl(217, 100%, 97%);
$alabaster: hsl(231, 100%, 99%);
$white: hsl(0, 0%, 100%);

main {
  h1 {
    color: rgb(253, 12, 12);
    &:hover {
      color: green;
    }
  }
}
</style>
