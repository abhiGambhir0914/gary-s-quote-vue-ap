<template>
    <div class="container">
        <app-new-quote @quoteAddEmit="newQuote"></app-new-quote>
        <app-quote-grid :quotes="quotesArray"></app-quote-grid>
    </div>
</template>

<script>
    import quoteGrid from './components/quoteGrid.vue';
    import newQuote from './components/newQuote.vue';

    export default {
        data: function(){
            return{
                quotesArray: [
                    'Legacy is greater than currency.',
                    'Without hustle, your talent will only get you so far.'
                    ],
                maxQuotes: 10
            }
        },
        methods:{
            newQuote(quote){
                this.quotesArray.push(quote);
            }
        },
        components: {
            appQuoteGrid: quoteGrid,
            appNewQuote: newQuote
        }
    }
</script>

<style>
</style>
