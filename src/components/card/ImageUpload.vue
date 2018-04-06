<template>
    <div class="row">
        <div class="col-lg-12">
            <h4>Upload image:</h4>
            <div class="form-group">
                <input type="file" class="form-control-file" id="fileUpload" @change="fileUpload">
            </div>
                <progress value="0" max="100" id="progressBar"></progress>
            <br>
            <img id="image">
            <button type="button" id="setImageButton" @click="setImage" style="display:none">Set Image</button>
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
                document.getElementById('setImageButton').style.display = 'none';
                console.log(event);
                this.file = event.target.files[0];
                var storageRef = Firebase.storage().ref("user_uploads/" + this.file.name);
                var upload = storageRef.put(this.file)

                var reader = new FileReader()
                reader.readAsDataURL(this.file);
                console.log(reader);
                reader.onload = function(e) {
                  document.getElementById('image').src = e.target.result;
                }

                upload.on('state_changed', function(snapshort){
                    var progress = (snapshort.bytesTransferred / snapshort.totalBytes) * 100;
                    document.getElementById('progressBar').value = progress;

                    if (progress === 100) {
                         document.getElementById('setImageButton').style.display = 'inline-block';
                    }
                })
            },
            setImage: function(){
                this.$emit('displayImageName', this.file.name);
            }
        }
    }
</script>

<style scoped>
img{
    max-width: 200px;
}
</style>
