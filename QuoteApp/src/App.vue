<template>
    <div class="container">
        <my-header :quoteCount="quotes.length" :max-quotes="maxQuotes"></my-header>
        <new-quote @quoteAdded="newQuote"></new-quote>
        <quote-grid :quotes="quotes" @quoteDeleted="deleteQuote($event)"></quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a Quote to delete it</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';

    export default {
        data(){
            return {
                quotes: [
                    'Just a Quote'
                ],
                maxQuotes: 10,
            }
        },
        methods: {
            newQuote(quote){
                this.quotes.push(quote);
            },
            deleteQuote(index){
                this.quotes.splice(index, 1);
            }
        },
        components: {
            QuoteGrid,
            NewQuote,
            'myHeader': Header
        }
    }
</script>

<style>
</style>
