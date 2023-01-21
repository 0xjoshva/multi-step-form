<template>
  <section>
    <div class="header">
      <h1>Personal info</h1>
      <p>Please provide your name, email address, and phone number.</p>
    </div>
    <form action="">
      <div class="label-container">
        <label for="name">
          <div class="label">
            <p>Name</p>
            <p class="warning" v-show="emptyField">This field is required</p>
          </div>
          <input
            type="text"
            placeholder="e.g. Stephen King"
            :class="{ redBorder: emptyField }"
            v-model="name"
          />
        </label>
        <label for="email">
          <div class="label">
            <p>Email Address</p>
            <p class="warning" v-show="emptyField">This field is required</p>
          </div>

          <input
            type="email"
            placeholder="e.g. stephenking@lorem.com"
            :class="{ redBorder: emptyField }"
            v-model="email"
          />
        </label>
        <label for="pnumber">
          <div class="label">
            <p>Phone Number</p>
            <p class="warning" v-show="emptyField">This field is required</p>
          </div>
          <input
            type="text"
            placeholder="e.g. +27 234 567 6890"
            :class="{ redBorder: emptyField }"
            v-model="pnumber"
          />
        </label>
      </div>
      <NuxtLink to="/step-2" class="nxtBtn">Next Step</NuxtLink>
    </form>
  </section>
</template>

<script>
export default {
  data() {
    return {
      emptyField: false,
    };
  },
};
</script>

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

section {
  font-family: $myFont;
  width: 30rem;
  height: 100%;
  background-color: $white;
  .header {
    padding-top: 1rem;
    margin-bottom: 2rem;
    h1 {
      color: $marineBlue;
      font-size: 2.4rem;
    }
    p {
      color: $coolGray;
      font-weight: 400;
      font-size: 1.1rem;
    }
  }
  form {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 32rem;
    align-items: flex-end;
    justify-content: space-between;

    .label-container {
      width: 100%;
      height: fit-content;
      display: flex;
      flex-direction: column;
      row-gap: 1rem;

      label {
        width: 30rem;
        .label {
          width: 100%;
          display: flex;
          justify-content: space-between;
          margin-bottom: 0.3rem;
          p {
            font-weight: 400;
            color: $marineBlue;
            font-size: 1rem;
          }
          .warning {
            color: $strawberryRed;
            font-weight: 500;
          }
        }

        input {
          width: 100%;
          padding: 0.8rem;
          border-radius: 8px;
          font-size: 1.1rem;
          border: none;
          border: 1px solid $lightGray;
          font-weight: 500;
          color: $marineBlue;
          outline: none;
          transition: 0.4s ease all;

          &:focus {
            border: 1px solid $purplishBlue;
          }
        }
      }
    }

    .nxtBtn {
      height: fit-content;
      width: width;
      padding-inline: 1.7rem;
      padding-block: 0.8rem;
      border: none;
      background: $marineBlue;
      color: $white;
      font-weight: 500;
      font-size: 1.1rem;
      border-radius: 12px;
      transition: 0.4s ease all;

      &:hover {
        filter: brightness(140%);
      }
    }
  }
  ::placeholder {
    font-weight: 500;
    color: $coolGray;
  }
  .redBorder {
    border: 1px solid $strawberryRed;
  }
}
</style>
