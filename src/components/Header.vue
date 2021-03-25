<template>
  <header class="header">
    <div class="banner" style="background-image: url(img/header.jpg)"></div>
    <div class="text-box">
      <h3>29th October 2021</h3>
      <p>Countdown here...</p>
      <h1>Daniel &amp; Annise</h1>
      <hr>
      <h2>The Wedding</h2>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="scss" scoped>
.header {
  position: relative;
  height: 250px;
  .banner {
    height: 250px;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
  }
  .text-box {
    position: absolute;
    bottom: 0;
    background: rgba(46, 46, 46, 0.7);
    padding: 10px;
    hr {
      width: 60px;
    }
    h1 {
      font-size: 2.1rem;
      color: white;
    }
    h2 {
      font-size: 1.5rem;
      color: white;
      text-transform: uppercase;
    }
    h3, p {
      color: white;
    }
  }
}
</style>