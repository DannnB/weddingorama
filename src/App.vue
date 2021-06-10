<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link>
    </div> -->
    <router-view/>
  </div>
</template>

<style lang="scss">
$purple: #6A4964;
#app {
  font-family: 'Source Sans Pro', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #454545;
  font-size: 16px
}


h1, h2, h3, h4, p {
  font-family: 'Source Sans Pro', sans-serif;
  font-weight: 300;
}

h1 {
  font-size: 2rem;
  font-weight: 400;
}
h2 {
  font-size: 1.8rem;
}
h3 {
  font-size: 1.6rem;
}

h1, h2, h3, h4 {
  margin: 2px 0;
}

.title {
  margin: 10px 0;
  &.is-3 {
    font-size: 1.4rem;
  }
  &.is-4 {
    font-size: 1.15rem;
  }
}
#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

button {
  &.btn {
    width: 65%;
    border-radius: 0;
    border: 1px solid $purple;
    height: 44px;
    font-size: 1.2rem;
    background: transparent;
    color: $purple;
    cursor: pointer;
    margin-top: 16px;
    &.active {
      background: $purple;
      color: white;
    }
    &:nth-child(2) {
      // margin-left: 10px;
    }
  }
  &.btn-primary {
    background: $purple;
    color: white;
  }
  &.btn-seconday {
  }
  &.disabled {
    cursor: not-allowed;
    opacity: .4;
  }
}
</style>
