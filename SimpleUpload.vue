<template>
    <form @submit.prevent="sendFile" enctype="multipart/form-data">
    <div class="field">
        <label for="file" class="label">Upload File</label>
        <input
        type="file"
        ref="file"
        @change="selectFile"
        />
    </div>
    <div class="field">
        <button class="button is-info">Send</button>
    </div>
    </form>
</template>

<script>
import axios from 'axios';

export default {
    name: "SimpleUpload",
    data(){
        return{
            file:""
        }
    },
    methods:{
        selectFile(){
            this.file= this.$ref.file.files[0];
        },
       async sendFile(){
            const formData = new FormData();
            formData.append('file',this.file);
            try{
                 await  axios.post('/upload', formData);
            }catch(err){
                console.log(err);
            }
            
        }

    }
}
</script>