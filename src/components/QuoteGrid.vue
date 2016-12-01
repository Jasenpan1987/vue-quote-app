<template>
    <div class="row">
        <app-quote v-for="(quote, idx) in quotes" @click.native="deleteQuote(idx)">
            {{ quote}}
        </app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';

    export default {
        props: ["quotes"],
        methods: {
            deleteQuote(idx){
                console.log('trigger from grid '+idx)
                this.$emit("deleteQuote", idx);
            }
        },
        components: {
            appQuote: Quote
        }
    }
</script>

<style>

</style>