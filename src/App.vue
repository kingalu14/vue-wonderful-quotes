<template>
    <div class="container">
         <app-new-quote @quoteAdded="newQuote"></app-new-quote>
         <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid> 
         <div class="row">
             <div class="col-smm-12 text-center">
                 <div class="alert alert-info">
                     click on quote to delete it!
                 </div>
             </div>

         </div>
    </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
    export default {
        data:function(){
            return{
                quotes:[
                       {title:"My first Quote",content:"Yaa Allah cure my pain"}
                ],
                maxQuote:10,
            }
        },
        methods:{
           newQuote(quote){
               this.quotes.push(quote);
               console.log(quote)
              
           },
           deleteQuote(index){
               const quote = [...this.quotes];
               quote.splice(index,1);
               this.quotes=quote;
           },
 
        },
        components:{
            appQuoteGrid:QuoteGrid,
            appNewQuote:NewQuote,
        }
        
    }
</script>

<style>
</style>
