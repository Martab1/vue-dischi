<template>
   <div class="card flex">
            <div class="flex">
                <img :src= "info.poster" :alt="info.title">
            </div>

            <div class="details ">
                <h3> <a href="#">{{info.title}}</a></h3>
                <div>{{info.author}}</div>
                <div>{{info.year}}</div>
                <a  class="little-font" href="#">{{info.genre}}</a>
            </div>
        
   </div>
</template>

<script>


export default {
      name: "Disc",
      props: ["info"],
}
</script>



<style scoped lang="scss">
@import "../styles/vars.scss";


.card{
    width: 170px;
    height: 350px;
    padding-top: 10px;
    background: $primary;
    margin: 0 15px;
    align-items: center;
    &:nth-child(3n){
        padding: 12px 0;
    }      
}

img{
    width: 130px;
   
}

.details {
    text-align: center;
    padding: 10px 10px;
    padding-bottom: 50px;
       div {
            padding: 5px 0;
            color:$text;
            font-size: 14px;           
    }
}

h3{
    font-weight: 400;
    font-size: $h3size;
    text-transform: uppercase;
    margin: 10px 0;
    
}



</style>