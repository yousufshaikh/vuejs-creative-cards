<template>
    <div class="img-container" :style="styleObj">
        <img id="outputImage">{{displayImage}}
    </div>
</template>

<script>
import Firebase from 'firebase'
    export default{
        props:{
            displayImage:{
                type: String
            },
            containerHeight: {
                type: Number,
                default: 200
            }
        },
        watch:{
            displayImage: function(){
                var storageRef = Firebase.storage().ref("user_uploads/" + this.displayImage);
                storageRef.getDownloadURL().then(function(url){
                    var img = document.getElementById('outputImage')
                    img.src = url
                })
            }
        },
        computed:{
            styleObj: function(){
                return{
                    height: this.containerHeight + 'px'
                }
            }
        }
    }
</script>

<style scoped>
.img-container{
    border: 1px dotted gray;
    overflow: hidden;
    margin: 5px 0;
}
</style>
