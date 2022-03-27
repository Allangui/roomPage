<template>
  <TopPage/>
  <BottomPage/>

</template>

<script>
import topPage from "./components/topPage.vue"
import bottomPage from "./components/bottomPage.vue"

export default{
  components: {
    TopPage : topPage,
    BottomPage : bottomPage
  },
}
</script>

<style lang="scss" >
html {
  box-sizing: border-box;
  font-size: 12px;
  margin: 0;
  padding: 0;
}

*, *:before, *:after {
  box-sizing: inherit;
}

body, h1, h2, h3, h4, h5, h6, p, ol, ul {
  margin: 0;
  padding: 0;
  font-weight: normal;
}

ol, ul {
  list-style: none;
}

img {
  max-width: 100%;
  height: auto;
}
#app {
  font-family: 'Spartan', sans-serif;
}
</style>
