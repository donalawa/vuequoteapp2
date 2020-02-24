<template>
    <div class="row">
        <app-quote v-for="(quote,index) in allQuote" :key="index" @click.native="deleteQuote(index)">
            <template slot="content">{{ quote.quote }}</template>
            <template slot="sub-title">{{ quote.author }}</template>
        </app-quote>
    </div>
</template>


<script>
import Quote from './Quote'
export default {
    name: 'quotegrid',
    props: ['allQuote'],
    components: {
        'app-quote': Quote
    },
    methods: {
        deleteQuote(ind){
            this.$emit('delete',ind)
        }
    }
  }
</script>

<style>
        .row {
         background-color: #eceff1;
         padding: 20px;
    }

</style>