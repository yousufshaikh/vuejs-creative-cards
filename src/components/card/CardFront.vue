<template>
    <div class="row">
        <div class="col-sm-6 card card-input" >
            <TextInputArea @displayTextOutput = 'inputAreaOne = $event'/>
            <ImageUpload @displayImageName = 'imageName = $event'/>
            <hr>
            <TextInputArea @displayTextOutput = 'inputAreaTwo = $event'/>
            <TextInputArea @displayTextOutput = 'inputAreaThree = $event'/>
        </div>
        <div class="col-sm-6 card card-output">
            <TextOutputArea :displayText="inputAreaOne" :containerHeight ="130"/>
            <ImageOutput :displayImage="imageName" :containerHeight ="350"/>
            <TextOutputArea :displayText="inputAreaTwo" :containerHeight="130"/>
            <TextOutputArea :displayText="inputAreaThree" :containerHeight="130"/>                       
        </div>
    </div>
</template>

<script>
import TextInputArea from './TextInputArea'
import TextOutputArea from './TextOutputArea'
import ImageUpload from './ImageUpload'
import ImageOutput from './ImageOutput'

export default{
    data: function(){
        return{
            inputAreaOne: '',
            inputAreaTwo: '',
            inputAreaThree: '',
            imageName:''
        }
    },
    components: {
        TextInputArea,
        TextOutputArea,
        ImageUpload,
        ImageOutput
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
