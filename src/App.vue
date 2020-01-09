<template>
  <v-app>
    <Navbar></Navbar>
    <Content></Content>
  </v-app>
</template>

<script>
import Navbar from './components/navabar'
import Content from './components/content'
export default {
  name: 'App',
  components: {
    Navbar,
    Content
  }
};
</script>
