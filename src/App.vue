<template>
    <div class="container">
        <app-bar :quoteCount="quotesArray.length" :maxQuotes="maxQuotes"></app-bar>
        <app-new-quote @quoteAddEmit="newQuote"></app-new-quote>
        <app-quote-grid :quotes="quotesArray" @quoteDeleted="deleteQuote"></app-quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on Quote to delete it!</div> 
            </div> 
        </div>      
    </div>
</template>

<script>
    import quoteGrid from './components/quoteGrid.vue';
    import newQuote from './components/newQuote.vue';
    import bar from './components/bar.vue'

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
                if(this.quotesArray.length >= this.maxQuotes){
                    return alert('Please delete some quotes first');
                }
                this.quotesArray.push(quote);
            },
            deleteQuote(index){
                this.quotesArray.splice(index,1);
            }
        },
        components: {
            appQuoteGrid: quoteGrid,
            appNewQuote: newQuote,
            appBar: bar
        }
    }
</script>

<style>
</style>
