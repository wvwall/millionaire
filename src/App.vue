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
    padding: 18px 10px;
    background-color: #0d0e8d;
    .logo {
      width: 200px;
    }
  }
  .bg_container {
    height: 100vh;
    background-color: #11093a;
    .container {
      padding: 15px;
      .box {
        border: 2px solid #fff;
        padding: 25px;
        color: #fff;
        font-weight: bold;
        font-size: 1.2rem;
        width: 70%;
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
          cursor: pointer;
          width: auto;

          border-radius: 20px;
          padding: 18px;
          @media (max-width: 768px) {
            width: 100%;
          }
        }
      }
      .container_result {
        i {
          font-size: 80px;
          display: none;
          &.fa-check-circle {
            color: chartreuse;
          }
          &.fa-times-circle {
            color: crimson;
          }
          &.active {
            display: block;
          }
        }
        width: 200px;
        height: 100px;
        margin: 0 auto;
        display: flex;
        justify-content: space-around;
        align-items: center;
        margin-top: 20px;
      }
    }
  }
}
.about {
  display: flex;
  flex-direction: column;
  margin-top: 50px;
  div {
    width: 50%;
    margin: 0 auto;
    h2 {
      margin-top: 20px;
      color: crimson;
    }
  }
}

.green {
  background-color: chartreuse;
  border-radius: 15px;
}
.red {
  background-color: crimson;
  border-radius: 15px;
}
</style>
