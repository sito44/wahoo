<template>
  <div id="app">
    <div id="navBar">
      <h1>WAHOO</h1>
      <nav class="navigation">
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
      </nav>
    </div>
    <main>
      <router-view />
    </main>
  </div>
</template>

<script>

export default {
  data() {
    return {
      
    };
  },
  components: {
    
  },
};
</script>
<style lang="scss">
@import "./Sass/abstracts/_mixins.scss";
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(98, 113, 111);
  width: 100vw;
  height: 100vh;
  box-sizing: border-box;
  padding: 0;
  margin: 0;
  overflow-x: hidden;
  font-size: 62.5%;
  background-image: url("./assets/spiration-light.png");
  
  scroll-behavior: smooth;
}
#navBar {
  z-index: 500;
  background: linear-gradient(
    to right,
    rgba(255, 255, 255, 1),
    rgba(255, 255, 255, 0.4)
  );
  background-color: rgba(white, 0.8);
  width: 100%;
  padding: 0 0 0 0.5rem;
  box-shadow: 0 -1px 5px black;
  position: fixed;
  display: flex;
  justify-content: space-between;

  h1 {
    font-size: 2rem;
    font-family:Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
  }
  .navigation {
    font-size: 1.6rem;
    align-self: center;
    flex: 1 0 auto;
    padding-right: 1rem;
    text-align: right;
  }
  .route-link {
    transition: all 0.2s ease;
    font-weight: bold;
    color: #2c3e50;
    font-size: 1rem;
    padding: 0 0.8rem 0 0.8rem;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
main {
  margin-top: 6rem;
  margin-bottom: 10.8rem;
  @include respond(tab-land) {
    margin-bottom: 0;
  }
  @include respond(tab-port) {
    margin-bottom: 0;
  }
  @include respond(phone) {
    margin-bottom: 0;
  }
}
.flex-style {
  display: flex;
  flex-wrap: wrap;
}
</style>
