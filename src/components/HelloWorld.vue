<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>



<template>
  <h1>LIVESCORE</h1>
  Watch soccer around the world!
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;

}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
