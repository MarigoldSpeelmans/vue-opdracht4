<script>
export default {
  data() {
    return {
      titel: "Vue Fundamentals",
      intro: "lorem ipsum...",
      linkUrl: "https://vuejs.org",
      imageUrl: "./src/assets/barbie-logo.png",
      fullName: "Marigold Speelmans",
      age: 23,
      buttonVisibility: "display: block",

    };
  },
  methods: {
    changeText() {
      let randomNumber = Math.random();
      if (randomNumber < 0.5) {
        return "Wij verkopen de beste producten die je op de markt kan vinden"
      } else {
        return "wie zoekt die vindt"
      }
    },
    showRandom() {
      return Math.random();
    },
    showButton(visible) {
      if (visible)
        this.buttonVisibility = "display: block"
      else
        this.buttonVisibility = "display: none"
    },
    changeImage(event, path) {
      event.target.textContent = 'Afbeelding gewijzigd'
      this.imageUrl = path
    }
  }
}

</script>

<template>
  <h1>{{ titel }}</h1> <!--hier gaat het om een parameter-->
  <p>{{ intro.toUpperCase() }}</p>
  <a v-bind:href="linkUrl" target="_blank">Website Vue.js
    <img alt="logo" :src="imageUrl" width="200">
  </a>
  <p>{{ changeText() }}</p> <!--hier gaat het om een functie-->
  <h2>{{ fullName }}</h2>
  <p>Age: {{ age }}</p>
  <p>Age + 5: {{ age + 5 }}</p>
  <p>{{ showRandom() }}</p>
  <div>
    <a v-bind:href="linkUrl" target="_blank">Website Vue.js</a>
  </div>
  <div>
    <input id="name" type="text" :value="fullName">
  </div>
  <hr>
  <div>
    <img alt="logo" :src="imageUrl" width="200" v-on:click="showButton(true)">
  </div>
  <button v-bind:style="buttonVisibility" @click="showButton(false)">Verberg mij</button>
  <div>
<!--    Deel 8-->
<!--    <button @click="changeImage('scr/assets/images/html.png')">Wijzig afbeelding</button>-->
<!--Deel 9-->
    <button @click="changeImage($event, 'scr/assets/images/html.png')">Wijzig afbeelding</button>
  </div>
</template>

<style>
</style>