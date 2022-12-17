<template>
  <main>
    <div class="box">
      <div class="sidebar">
        <NuxtLink :to="r.route" class="router-link" v-for="r in routerItems" :key="r.step">
          <div class="circle"><p>{{r.step}}</p></div>
          <div class="info">
            <div class="step">STEP {{r.step}}</div>
            <div class="step-header">{{r.title}}</div>
          </div>
        </NuxtLink>
      </div>
      <div class="content">
        <slot />
      </div>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      routerItems: [
        {
          step: 1,
          title: "your info",
          route: "/",
        },
        { step: 2, title: "select plan", route: "/selectplan" },
        { step: 3, title: "add-ons", route: "/add-ons" },
        { step: 4, title: "summary", route: "/summary" },
      ],
    };
  },
};
</script>

<style lang="scss">
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
  background: $magnolia;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: $myFont;
  .box {
    width: 64rem;
    height: 75vh;
    background: $white;
    border-radius: 16px;
    box-shadow: 4px 5px 20px 0px rgb(0 0 0 / 8%);
    padding: 1.5rem;
    display: flex;
    justify-content: space-between;
    padding-right: 6rem;

    .sidebar {
      background-color: $purplishBlue;
      background-image: url(../assets/bg-sidebar-desktop.svg);
      background-position: bottom;
      background-repeat: no-repeat;
      background-size: cover;
      width: 20rem;
      height: 100%;
      border-radius: 12px;
      padding: 2rem;
      padding-top: 3rem;
      display: flex;
      flex-direction: column;
      row-gap: 2rem;
      .router-link {
        display: flex;
        height: 45px;
        column-gap: 1rem;
        .circle {
          width: 45px;
          height: 100%;
          padding: 1rem;
          border: 1px solid $white;
          border-radius: 50%;
          display: flex;
          align-items: center;
          justify-content: center;
          p {
            text-decoration: none;
            color: $white;
            font-weight: 600;
            font-size: 1.1rem;
            line-height: 1.1rem;
          }
        }
        .info {
          display: flex;
          flex-direction: column;
          width: 100%;
          height: 100%;
          justify-content: space-between;
          .step {
            color: $pastelBlue;
            font-size: .9rem;
            height: fit-content;
            width: 100%;
          }
          .step-header {
            color: $white;
            font-weight: 500;
            font-size: 1.1rem;
            height: fit-content;
            width: 100%;
            text-transform: uppercase;
          }
        }
      }
    }
    .router-link-exact-active {
      .circle {
        background: $lightBlue;
        border: 1px solid $lightBlue !important;
        p {
          color: $marineBlue !important;
          font-size: 1.1rem;
          line-height: 1.1rem;
        }
      }
    }
        .content{
          width: 30rem;
          height: 100%;
        }
  }
}
a {
  text-decoration: none;
}
</style>
