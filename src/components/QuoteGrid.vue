
<template>
   <div class="row">
       <app-quote v-for="(quote,i) in quotes" :key=i @click.native="deleteQuote(i)">
          <h2>{{quote.title}}</h2>
          <p>{{quote.content}}</p>
       </app-quote></div>  
</template>

<script>
import Quote from './Quote.vue'
export default {
    props:{
        quotes:{
            title:"",
            content:""
        } , 
    
    },
    components:{
        appQuote:Quote
    },
    methods:{
        deleteQuote(i){
              this.$emit('quoteDeleted',i);
              console.log(i);
        }
    }
}
</script>

<style>


</style>

