<template>
    <div class="img-container" :style="styleObj" @mouseover="showOptions=true" @mouseleave="showOptions=false">
        <img id="outputImage">{{displayImage}}
        <!-- <button class="btn btn-outline-danger btn-sm" v-show="showOptions">Remove Image</button> -->
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
        data: function(){
            return{
                showOptions: false
            }
        },
        watch:{
            displayImage: function(){
                var storageRef = Firebase.storage().ref("user_uploads/" + this.displayImage);
                storageRef.getDownloadURL().then(function(url){
                    var img = document.getElementById('outputImage')
                    img.src = url
                    setDragable()
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
    function setDragable() {
        $('#outputImage').draggable();
    }
</script>

<style scoped>
.img-container{
    border: 1px dotted gray;
    overflow: hidden;
    margin: 5px 0;
}
img{
    width: 130%;
}
</style>
