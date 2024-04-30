<template>
  <main>
    <div class="page">
      <img src="../assets/logo.png" alt="brand-logo" id="brandLogo"/>
      <h3>Wer spielt&quest;</h3>
      <input v-model="playerName" id="player" placeholder="Name">
      <button class="close">
        <RouterLink :to="{ path: '/game', query: { player: playerName } }"  id="play">Spielen</RouterLink>
      </button>
    </div>
    <div class="gradient"></div>
  </main>
</template>

<script lang="js">
export default {
  data() {
    return {
      playerName: '' // Initialisieren des Spielernamens
    };
  },
  mounted() {
    document.addEventListener("mousemove", this.onMouseMove);
  },
  methods: {
    onMouseMove(event) {
      const gradient = document.querySelector(".gradient");
      gradient.style.backgroundImage = `radial-gradient(at ${event.clientX}px ${event.clientY}px, rgba(159,0,191,.9) 0, #4D4FA7 70%)`;
    },
  },
};
</script>

<style>
@import "@/assets/home.css";
</style>
