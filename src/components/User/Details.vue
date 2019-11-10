<template>
    <div>
        <div class="card">
            <div class="d-flex justify-content-center">
                <span><p class="text-monospace">Submitted names</p></span>
            </div>
            <div class="card-body">
                <ul v-for="(name, index) in names" :key="index" class="list-group list-group-flush">
                    <li class="list-group-item">{{ name }}</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>

import { bus } from '../../main.js'

export default {
    data(){
        return {
            names: ['Ken', 'Peter', 'Maina']
        }
    },
    created(){

        bus.$on('submitName', (value)=>{
            this.names.push(value)
        })

    }
    
}
</script>

<style lang="">
    
</style>