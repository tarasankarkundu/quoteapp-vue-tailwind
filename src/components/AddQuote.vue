<template>
    <div>
        <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
            <label class="block text-gray-700 text-sm font-bold mb-2">Quote</label>
            <textarea v-model="quoteText" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"></textarea>
            <div class="md:flex md:items-center mt-2">
                <button @click.prevent="addQuote" class="m-auto shadow bg-blue-500 hover:bg-blue-400 focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded ">Add</button>  
            </div>
        </form>
    </div>
    
</template>
<script>
export default {
    data(){
        return {
            quoteText: ''
        }
    },
    methods:{
        addQuote(){
            this.$emit('newQuoteAdded', this.quoteText);
            this.quoteText = '';
        }
    }
}
</script>
<style scoped>

</style>