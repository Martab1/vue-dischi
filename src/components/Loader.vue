<template>
    <div class="content">
        <div class="loader">
            <div class="text">loading...</div>
        </div>
        
    </div>
</template>

<script>
export default {
     name: "Loader",
}
</script>

<style scoped lang="scss">
@import "../styles/vars.scss";

.content{
    position: absolute;
    top: 40%;
    left: 50%;
 
}

.loader,
.loader:before,
.loader:after {
  background: $primary;
  animation: load1 1s infinite ease-in-out;
  width: 1em;
  height: 4em;

}

.loader {
  color: $primary;
  position: relative;
  font-size: 20px;
  animation-delay: -0.16s;
  &:before,
  &:after{
        content: '';
        position: absolute;
        bottom: 0;
  } &:before{
       left: -1.5em;
       animation-delay: -0.32s;
  }    &:after{
      left: 1.5em;
  }
}

@keyframes load1 {
  0%,
  80%,
  100% {
    box-shadow: 0 0;
    height: 4em;
  }
  40% {
    box-shadow: 0 -2em;
    height: 5em;
  }
}

.text{
    position: absolute;
    bottom: -50px;
    right: -80px;
    font-size: 2rem;
    text-transform: uppercase;
   
}

</style>