<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!server">Please select a server</p>
        <p v-else>Server #{{server.id}} selected, Status: {{server.status}}</p>
        <hr>
        <button @click="changeToNormal">Change server status to Normal</button>
    </div>

</template>

<script>
    import {EventBus} from "../../main";

    export default {
        data() {
            return {
                server: null
            }
        },
        methods: {
            changeToNormal(){
                this.server.status = 'Normal'
            }
        },
        created() {
            EventBus.$on('loadServer', (server) => {
                this.server = server;
            })
        }
    }
</script>

<style>

</style>
