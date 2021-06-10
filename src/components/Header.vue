<template>
  <header class="header">
    <!-- <div class="banner" style="background-image: url(img/header.jpg)"></div> -->
    <h1 class="title">Annise O'Connell <br> &amp; <br> Daniel Broughton</h1>
    <p class="large">Request the pleasure of your company at the celebration of thier wedding.</p>
    <div class="intro-text">
      <h2>Friday 29th October 2021</h2>
      <h3>12 noon - Ceremony <br> 7pm Evening Reception</h3>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="scss" scoped>
.title {
  line-height: 34px;
  margin: 30px 0;
  font-size: 2.3rem;
}
.large {
  font-size: 1.4rem;
}
.header {
  // position: relative;
  // height: 250px;
  .intro-text {
    h2 {
      font-size: 2rem;
    }
  }
  .banner {
    // height: 250px;
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