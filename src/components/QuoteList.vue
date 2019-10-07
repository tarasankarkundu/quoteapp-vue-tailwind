<template>
<div>
    <div class="flex flex-wrap">
        <app-quote v-for="(quote, i) in quotes" :key="i" @click.native="deleteQuote(i)">
            {{quote}}
        </app-quote>
    </div>
</div>
    
</template>
<script>
import Quote from "./Quote.vue";
export default {
    props: [
        'quotes',
        'deleteQuote'
    ],
    components:{
        appQuote: Quote
    }
}
</script>
<style scoped>

</style>