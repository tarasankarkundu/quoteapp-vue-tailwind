<template>
    <div>
        <app-header :quoteCount="quotes.length" :maxQuotes="maxLimit"></app-header><br>
        <app-new-quote @newQuoteAdded="addQuote"> </app-new-quote>
        <app-quote-list :quotes="quotes" :deleteQuote="deleteQuote"></app-quote-list>

        <div class="row">
            <div class=" flex text-center text-center items-center bg-red-200 m-2 p-4">
                <div class="flex-1">Info: Click on a Quote to delete it!</div>
            </div>
        </div>
    </div>


</template>

<script>
    import Progressbar from './components/Progressbar.vue';
    import AddQuote from './components/AddQuote.vue';
     import QuoteList from './components/QuoteList.vue';
     
    export default {
        data() {
            return {
                quotes: ['This is a sample quote'], 
                maxLimit: 10
            }
        },
        methods:{
            addQuote(quote){
                if (this.quotes.length >= this.maxLimit) {
                    return alert('Please delete Quotes first!');
                }
                this.quotes.push(quote);
            },
            deleteQuote(index){
                this.quotes.splice(index, 1);
            }
        },
        components: {
            appQuoteList: QuoteList,
            appNewQuote: AddQuote,
            appHeader: Progressbar
        }

    }
</script>

<style>
</style>
