<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" /> -->
    <div class="box">
      <div class="shadow"></div>
      <div class="gravity">
        <div class="ball"></div>
      </div>
    </div>

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Live</RouterLink>
        <RouterLink to="/about">Highlights</RouterLink>
      </nav>


      <form>
    <select id="competitions" v-model="store.competition_selected">
      <option value="ARGENTINIA: Primera Nacional">ARGENTINIA: Primera Nacional</option>
      <option value="BRAZIL: Serie A">BRAZIL: Serie A</option>
      <option value="CHAMPIONS LEAGUE: FINAL">CHAMPIONS LEAGUE: FINAL</option>
      <option value="CHINA: Super League">CHINA: Super League</option>
      <option value="COPA LIBERATORES: GROUP STAGE">COPA LIBERATORES: GROUP STAGE</option>
      <option value="ENGLAND: Premier League">ENGLAND: Premier League</option>
      <option value="ENGLAND: FA Cup">ENGLAND: FA Cup</option>
      <option value="FRANCE: Ligue 1">FRANCE: Ligue 1</option>
      <option value="INTERNATIONAL: Club Friendlies">INTERNATIONAL: Club Friendlies</option>
      <option value="ITALY: Serie A">ITALY: Serie A</option>
      <option value="JAPAN: J-League">JAPAN: J-League</option>
      <option value="MEXICO: Apertura">MEXICO: Apertura</option>
      <option value="MYANMAR: National League">MYANMAR: National League</option>
      <option value="SPAIN: La Liga">SPAIN: La Liga</option>
      <option value="UEFA NATIONS LEAGUE A, Playoffs">UEFA NATIONS LEAGUE A, Playoffs</option>
      <option value="WORLD: INTERNATIONAL FRIENDLIES">WORLD: INTERNATIONAL FRIENDLIES</option>
    </select>
  </form>
  
    </div>

  </header>



  <RouterView />
</template>

<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import { store } from "@/store";
</script>

<script>
export default {
  name: "CompetitionSelect",
  data() {
    // hier wird ein JS Objekt mit alle Daten erstellt
    return {}
  },
  created() {
    // Wir einmalig gestartet

  },
  methods: {
    
  },
  };
</script>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: hsla(160, 100%, 37%, 1);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}

.box {
  margin: 0 auto;
  width: 140px;
  height: 140px;
  position: relative;

  .shadow {
    position: absolute;
    width: 40%;
    height: 10px;
    background-color: grey;
    bottom: 0;
    border-radius: 100%;
    transform: scaleX(.8);
    opacity: .6;
    animation: shadowScale 1.5s linear infinite;
  }
}

.gravity {
  width: 40px;
  height: 40px;
  animation: bounce 1.5s cubic-bezier(0.68, 0.35, 0.29, 0.54) infinite;
}

.ball {
  width: 40px;
  height: 40px;
  background-image: url('https://cdn2.iconfinder.com/data/icons/activity-5/50/26BD-soccer-ball-128.png');
  background-size: cover;
  animation: roll .7s linear infinite;
}

@keyframes roll {
  0% {}

  100% {
    transform: rotate(360deg)
  }
}

@keyframes bounce {
  0% {}

  50% {
    transform: translateY(100px)
  }

  100% {}
}

@keyframes shadowScale {
  0% {}

  50% {
    transform: scaleX(1);
    opacity: .8;
  }

  100% {}
}
</style>
