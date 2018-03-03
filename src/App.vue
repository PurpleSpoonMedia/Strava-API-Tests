<template>
  <div id="app">
    <header>
      <div class="container">
        <img src="@/assets/strava_logo.png" />
        <ul class="nav">
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/Linda">Linda</router-link></li>
        </ul>
      </div>
    </header>

    <div class="container">
      <router-view/>
    </div>

    <footer>
      <div class="container">&copy; Linda Stuurman &nbsp;&nbsp;&nbsp;Powered by Strava</div>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="scss">
body {margin:0;padding:0;}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
header {
  background:#def;
  overflow:hidden;
  padding:0 0 15px 0;
  margin-bottom:40px;
  & img {float:left;}
}
.container {
  max-width:1180px;
  margin: 0 auto;
}
.nav {
  list-style:none;
  padding:40px 0 0;
  & li {
    float:left;
    & a {
      background:#cde;
      padding:15px;
      border-left:3px solid #def;
      text-decoration:none;
      &.router-link-exact-active {
        background:#678;
        color:#fff;
      }
    }
    &:first-child a {
      border:0;
    }
  }
}
footer {
  background:#678;
  color:#fff;
  padding:15px 0;
  margin-top:40px;
}
</style>
