<template>
<div class="row">
    <div class="col-sm-12">
        <div class="form-group">
            <h4>Edit Text</h4>
            <textarea class="form-control" cols="50" rows="4" placeholder="Enter text here" 
                                            v-model="inputTextValue" @keyup="textChange"></textarea>
        </div>
    </div>
</div>
</template>

<script>
    export default{
        data: function(){
            return{
                inputTextValue: ''
            }
        },
        methods:{
            textChange: function(){
                this.$emit('displayTextOutput', this.inputTextValue)
            }
        }
    }
</script>

<style>

</style>

