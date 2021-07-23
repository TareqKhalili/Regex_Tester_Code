<template>
  <Header />
  <Body :savedExps="savedExps" :savedFlags="savedFlags" />
  <SavedExpressions :savedExps="savedExps" :savedFlags="savedFlags" />
  <Sheet />
</template>

<script>
import Header from "./components/Header.vue"
import Body from "./components/Body.vue"
import Sheet from "./components/CheatSheet.vue"
import SavedExpressions from "./components/SavedExpressions.vue"

export default {
  name: "App",

  components: {
    Header,
    Body,
    Sheet,
    SavedExpressions,
  },

  data() {
    return {
      savedExps: [],
      savedFlags: [],
    }
  },
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  text-align: center;
}
</style>
