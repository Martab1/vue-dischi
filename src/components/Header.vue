<template>
   <header>
       <!-- logo -->
         <img src="../assets/logo.png" alt="logo">
       
   </header>
</template>

<script>
export default {
    name: "Header",

}
</script>

<style scoped lang="scss">
@import "../styles/vars.scss";

header{
    padding: 5px;
    background: $primary;
}

img{
    width: 45px;
}
</style>