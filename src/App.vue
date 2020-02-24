<template>
    <div id="app" class="container">
      <app-header :max="maxQuote" :quoteLength="quotes.length"></app-header>
      <div class="alert alert-warning" v-if="showAlert"><p>Please Delete Some Quotes Before Adding More</p></div>
      <app-newquote @sendQuote="addNewQuote"></app-newquote>
      <app-quotegrid :allQuote="quotes" @delete="quoteDelete"></app-quotegrid>
    </div>
</template>


<script>
import  QuoteGrid from './components/QuoteGrid';
import NewQuote from './components/NewQuote';
import Header from './components/Header'
export default {
  name: 'app',
  data(){
    return {
      quotes:[
        {author: 'Mista_Zidane', quote: 'I love Food'},
        {author: 'Joy', quote: 'I am in class'},
        {author: 'Fadimatou', quote: 'Je suis en classe'},
        {author: 'Rene', quote: 'We love to code'},
        {author: 'D-Karl', quote: 'When you are hungry code'}
      ],
      maxQuote: 8,
      showAlert: false
    }
  },
  components: {
    'app-quotegrid': QuoteGrid,
    'app-newquote': NewQuote,
    'app-header': Header
  },
   methods: {
     addNewQuote(quote){
       if(this.quotes.length < this.maxQuote){
         this.quotes.push(quote)
       }
     },
     quoteDelete(ind){
       this.quotes.splice(ind,1)
     }
   },
   watch: {
     quotes: function(value){
       if(value.length == this.maxQuote){
         this.showAlert = true;
       }else {
         this.showAlert = false;
       }
     }
   }
}
</script>

<style>
@import '../node_modules/bootstrap/dist/css/bootstrap.min.css';
p {
  font-weight: bold;
}

</style>