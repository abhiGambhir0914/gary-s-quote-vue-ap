<template>
    <div class="container">
        <app-quote-grid :quotes="quotesArray"></app-quote-grid>
    </div>
</template>

<script>
    import quoteGrid from './components/quoteGrid.vue';

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
        components: {
            appQuoteGrid: quoteGrid
        }
    }
</script>

<style>
</style>
