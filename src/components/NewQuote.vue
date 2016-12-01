<template>
    <div class="row">
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label>New Quote</label>
                <textarea class="form-control" rows="3" v-model="quote"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>

    //import { eventBus } from '../main.js';

    export default {
        data(){
            return {
                quote: ''
            }
        },
        methods: {
            createNew(){
                //eventBus.$emit("createNewQuote", this.quote);
                this.$emit("createNewQuote", this.quote);
                this.quote = '';
            }
        }
    }
</script>