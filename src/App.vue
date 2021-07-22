<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 15px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
.home {
  .bg_logo {
    padding: 20px;
    background-color: #0d0e8d;
    .logo {
      width: 200px;
    }
  }
  .bg_container {
    height: 400px;
    background-color: #11093a;
    .container {
      padding: 15px;
      .box {
        border: 2px solid #fff;
        padding: 25px;
        color: #fff;
        font-weight: bold;
        font-size: 1.2rem;
        width: 80%;
        margin: 0 auto;
        border-radius: 10px;
      }
      .container-answ {
        width: 80%;
        margin: 0 auto;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        .box {
          width: 40%;
          margin: 15px;
          border-radius: 25px;
          padding: 18px;
          @media (max-width: 768px) {
            width: 100%;
          }
        }
      }
    }
  }
}
.about {
  display: flex;
  flex-direction: column;
  div {
    width: 50%;
    margin: 0 auto;
    h2 {
      color: crimson;
    }
  }
}
</style>
