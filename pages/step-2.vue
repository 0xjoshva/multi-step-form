<template>
  <section>
    <div class="header">
      <h1>Select your plan</h1>
      <p>You have the option of monthly or yearly billing</p>
    </div>
    <div class="container">
      <div
        class="item"
        v-for="t in tiers"
        :key="t.id"
        @click="selected = t.id"
        :class="{ selectedTier: selected === t.id }"
      >
        <img :src="t.imgDir" alt="" />
        <div class="bottom">
          <p class="title">{{ t.title }}</p>
          <div class="price">
            <p class="monthly-price" v-show="!yearly">${{ t.monthly }}/mo</p>
            <p class="yearly-price" v-show="yearly">${{ t.yearly }}/mo</p>
          </div>
          <p class="discount" v-show="yearly">2 months free</p>
        </div>
      </div>
    </div>
    <div class="bar">
<p class="monthly" :class="{highlighted : !yearly}">Monthly</p>
<div class="slider">
    <input type="checkbox" id="toggle" class="offscreen" @click="yearly = !yearly"/>
<label for="toggle" class="switch"></label>
</div>
<p class="yearly" :class="{highlighted : yearly}">Yearly</p>
    </div>
    <div class="btn-div">
        <NuxtLink to="/">Go Back</NuxtLink>
        <NuxtLink to="/step-3">Next Step</NuxtLink>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      tiers: [
        {
          id: 1,
          title: "Arcade",
              monthly: 9,
          yearly: 90,
          imgDir:
            "https://raw.githubusercontent.com/0xjoshva/multi-step-form/8e1fce23b71c5db9fe18c25afb78bd5fac27f5b3/assets/icon-arcade.svg",
        },
        {
          id: 2,
          title: "Advanced",
            monthly: 12,
          yearly: 120,
          imgDir:
            "https://raw.githubusercontent.com/0xjoshva/multi-step-form/8e1fce23b71c5db9fe18c25afb78bd5fac27f5b3/assets/icon-advanced.svg",
        },
        {
          id: 3,
          title: "Pro",
            monthly: 15,
          yearly: 150,
          imgDir:
            "https://raw.githubusercontent.com/0xjoshva/multi-step-form/8e1fce23b71c5db9fe18c25afb78bd5fac27f5b3/assets/icon-pro.svg",
        },
      ],
        selected: null,
      yearly: false
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
  .container {
    width: 100%;
    display: flex;
    justify-content: space-between;
    column-gap: 1rem;
    .item {
      width: 33.33%;
      height: 11rem;
      border: 1px solid $lightGray;
      transition: ease 0.4s all;
      border-radius: 12px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding: 1rem;
      &:hover {
        border: 1px solid $purplishBlue;
      }

      img {
        width: 45px;
        height: auto;
      }
      .bottom {
        .title {
          color: $marineBlue;
          font-weight: 500;
          font-size: 1.1rem;
        }
        .price {
          font-weight: 500;
          color: $coolGray;
          font-size: 1rem;
        }
        .discount{
            font-size: 1rem;
            font-weight: 400;
            color: $marineBlue;
        }
      }
    }
  }
  .bar{
    width: 100%;
    height: 3rem;
    background: $magnolia;
    border-radius: 8px;
    margin-top: 2rem;
    display: flex;
    justify-content: center;
    align-items: center;
    column-gap: 1rem;
  }
  p{
    font-size: 1.1rem;
    font-weight: 500;
    color: $coolGray;
    transition: .4s ease all;
  }
  .slider{
    height: 100%;
    width: fit-content;
    display: flex;
    justify-content: center;
    align-items: center;
    .switch {
  position: relative;
  display: inline-block;
  width: 48px;
  height: 26px;
  background-color: $marineBlue;
  border-radius: 20px;
  transition: all 0.3s;
}

.switch::after {
  content: '';
  position: absolute;
  width: 15px;
  height: 15px;
  border-radius: 18px;
  background-color: white;
  top: 6px;
  left: 6px;
  transition: all 0.3s;
}

input[type='checkbox']:checked + .switch::after {
  transform: translateX(20px);
}

input[type='checkbox']:checked + .switch {
  background-color: $marineBlue;
}

.offscreen {
  position: absolute;
  left: -9999px;
}
  }
}
.selectedTier {
  background: $magnolia !important;
  border: 1px solid $purplishBlue !important;
}
.highlighted{
    color: $marineBlue !important;
}
</style>
