<template>
    <div class="row">
        <div class="col-sm-6 card card-input" >
            <TextInputArea @displayTextOutput = 'inputAreaOne = $event'/>
            <TextInputArea @displayTextOutput = 'inputAreaTwo = $event'/>
            <TextInputArea @displayTextOutput = 'inputAreaThree = $event'/>
        </div>
        <div class="col-sm-6 card card-output">
            <TextOutputArea :displayText="inputAreaOne" :containerHeight ="130"/>
            <TextOutputArea :displayText="inputAreaTwo" :containerHeight="130"/>
            <TextOutputArea :displayText="inputAreaThree" :containerHeight="130"/>                       
        </div>
    </div>
</template>

<script>
import TextInputArea from './TextInputArea'
import TextOutputArea from './TextOutputArea'

export default{
    data: function(){
        return{
            inputAreaOne: '',
            inputAreaTwo: '',
            inputAreaThree: ''
        }
    },
    components: {
        TextInputArea,
        TextOutputArea
    }
}
    
</script>

<style scoped>
.card-input{
    height: 800px;
    background-color:#d2f9f9;
    padding: 20px;
}
.card-output{
    height: 800px;
    padding: 20px;
}
</style>
