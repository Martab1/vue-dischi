<template>
   <main class="flex">
        <!-- disc container -->
        <div v-if= "!loading" class="main-container flex" >      
            <Disc v-for="(item,index) in discs.response" :key="index" :info="item"/>
        </div>
        <!-- loading -->
        <div class="load" v-else>
          <Loader/>
        </div>  
       
   </main>
</template>

<script>
// importo axios (APIs)
import axios from "axios";
// importo componente singolo disco
import Disc from "@/components/Disc.vue";
import Loader from "@/components/Loader.vue";

export default {
     name: "Main",
     components:{
        Disc,
        Loader,
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
                 this.discs = res.data;
                //  console.log(this.discs.response);
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
    background: $background;
    height: 95vh;
}





</style>