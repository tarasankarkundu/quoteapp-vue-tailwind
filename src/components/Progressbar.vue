<template>
    <div>
        <div class="shadow w-full bg-grey-light m-4">
            <div role="progressbar" class="bg-blue-500 text-xs leading-none py-1 text-center text-white" :style="{width: (quoteCount / maxQuotes) * 100 + '%'}">
                        {{ quoteCount }} / {{ maxQuotes}}</div>
        </div>
    </div>
     
</template>
<script>
export default {
    props: ['quoteCount', 'maxQuotes']
}
</script>
<style scoped>

</style>