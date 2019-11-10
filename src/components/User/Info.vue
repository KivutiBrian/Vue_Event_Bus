<template>
    <div>
        <div class="card">
            <div class="d-flex justify-content-center">
                <h3>{{ message }}</h3> 
                <button @click="changeMessage" class="ml-4 btn btn-sm btn-warning">Update message</button>
            </div>
            <div class="d-flex justify-content-center">
                <span><p class="text-monospace">Fill in the details below</p></span>
            </div>
            <div class="card-body">
                <div class="mb-2">
                    <span><p class="text-info">Press enter to submit name</p></span>
                    <input type="text" class="form-control" placeholder="First Name" v-model="fname" @keyup.enter="submitName">
                    <span v-if="showError"><p class="text-danger">Input cannot be blank</p></span>
                </div>
                
            </div>
        </div>
    </div>
</template>

<script>

import { bus } from '../../main.js'

export default {
    props: {
        message: String,
    },
    data(){
        return {
            fname: '',
            showError: false
        }
    },
    methods:{

        // submit
        submitName(){

            if (this.validateInput(this.fname)){
                bus.$emit('submitName', this.fname)
                this.fname = ''
                this.showError = false
            }else{
                this.showError = true
            }
        },

        // validate if the input field is blank
        validateInput(value){
            
            if (value !== ''){
                return true
            }else{
                return false
            }
        },

        // change message
        changeMessage(){
            this.$emit('Changename', 'Vuejs is really awesome')
        }
    }
    
}
</script>

<style>
    
</style>