<template>
   <main>
       <div  class="main-container flex"
             v-for= "(item,index) in discs" :key= "index" :info= "item"
       >
             
        <Disc/>
       </div>
   </main>
</template>

<script>
// importo axios (APIs)
import axios from "axios";
// importo componente singolo disco
import Disc from "@/components/Disc.vue";

export default {
     name: "Main",
     components:{
        Disc,
     },
     data(){
         return{
             apiURL : "https://flynn.boolean.careers/exercises/api/array/music" ,
             discs: [],
             loading: true,

         };
     },
     created(){
        this.getDiscs()
     },
     methods: {
         getDiscs(){
             // API CALL
             axios.get(this.apiURL)
             .then(res => {
                 console.log(res.data);
                 this.discs = res.data.response;
                 console.log(this.discs.response);
                 this.loading = false;
                 
             })
             .catch(error => {
                 console.log("Errore", error);
             });

         }
     }
}


</script>

<style scoped lang="scss">
//importo vars di stile
@import "../styles/vars.scss";

main{
    height: 100vh;
    background: $background;
}



</style>