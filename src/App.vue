<template>
    <div class="container">
        <h1>Quote App</h1>
        <progress-bar :quoteCount="quotes.length" :maxQuote="maxQuote"></progress-bar>
        <app-quote-grid :quotes="quotes" @deleteQuote="deleteQuoteListener"></app-quote-grid>
        <app-new-quote @createNewQuote="createNewQuoteListener"></app-new-quote>

        <div class="row">
            <div class="col-md-12">
                <div class="alert alert-info text-center">
                    <h4>Delete a quote by clicking it</h4>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

    //import { eventBus } from './main.js';

    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import ProgressBar from './components/ProgressBar.vue';

    export default {
        data(){
            return {
                quotes: [
                    "My Awesome Quote 1",
                    "Some Random Quote 2",
                    "Some Stupid Quote 3"
                ],
                maxQuote: 10
            }
        },

        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            progressBar: ProgressBar
        },
        methods: {
            createNewQuoteListener(content){
                if(this.quotes.length == this.maxQuote){
                    alert("Max number of quote!!!")
                }else{
                    this.quotes.unshift(content);
                }
            },
            deleteQuoteListener(idx){
                console.log('receive a event from grandchild '+idx)
                this.quotes.splice(idx, 1)
            }
        }
        /*created(){
            eventBus.$on("createNewQuote", (content) => {
                this.quotes.unshift(content);
            })
        }*/
    }
</script>

<style>
</style>
