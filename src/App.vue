<template>
  <section>
       <Header/>
       <Main/>
       <Disc/>
  </section>
</template>

<script>
import Header from "@/components/Header.vue";  //@ src
import Main from './components/Main.vue';
import Disc from './components/Disc.vue';

export default {
  name: 'App',
  components: {
     Header,
     Main,
     Disc,
  }
}
</script>

<style lang="scss">
//importo stili
@import "./styles/general.scss";
@import "./styles/utilities.scss";

</style>
