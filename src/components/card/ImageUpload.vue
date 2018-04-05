<template>
    <div class="row">
        <div class="col-lg-12">
            <h4>Upload image:</h4>
            <div class="form-group">
                <input type="file" class="form-control-file" id="fileUpload" @change="fileUpload">
            </div>
            <br>
            <img id="image">
            <button type="button" id="setImageButton">Set Image</button>
        </div>
    </div>
</template>

<script>
import Firebase from 'firebase'

    export default{
        date: function(){
            return{
                file: ''
            }
        },
        methods: {
            fileUpload: function(event){
                console.log(event);
                this.file = event.target.files[0];
                var storageRef = Firebase.storage().ref("user_uploads/" + this.file.name);
                storageRef.put(this.file)

                var reader = new FileReader()
                reader.readAsDataURL(this.file);
                console.log(reader);
                reader.onload = function(e) {
                    document.getElementById('image').src = e.target.result;
                }
            }
        }
    }
</script>

<style scoped>
img{
    max-width: 200px;
}
</style>
