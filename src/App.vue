<script>
import Header from './components/header/Header.vue';
import Main from './components/main/Main.vue';

export default {
  components: {
    Header,
    Main,
  },
}

</script>

<template>
  <Header></Header>
  <Main></Main>
  
</template>

<style lang="scss">
@use './styles/general.scss';

</style>
