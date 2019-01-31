<template>
    <li class="list-group-item">
        Server #{{ server.id }}
        <button @click="loadServerDetails">Load Server Details</button>
    </li>
</template>

<script>
    import {EventBus} from "../../main";

    export default {
        props: {
            server: Object
        },
        methods:{
            loadServerDetails(){
                EventBus.$emit('loadServer', this.server);
            }
        }
    }
</script>