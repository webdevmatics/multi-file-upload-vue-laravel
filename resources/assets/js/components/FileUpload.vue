<template>
    <div class="container">
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <div class="panel panel-default">
                    <div class="panel-heading">VUe Example Component</div>

                    <div class="panel-body">

                            <legend>Upload form</legend>

                            <div class="form-group">
                                <label>Upload Files</label>
                                <input type="file"  class="form-control" @change="fileChange">
                            </div>

                            <button @click.stop="uploadFile" class="btn btn-primary">Submit</button>

                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return{

                attachment:null,
                data:new FormData()
            }
         
        },
        methods:{
            fileChange(e){
                this.attachment = e.target.files[0];

            },
            uploadFile(){

                this.data.append('file',this.attachment);


                const config = { headers: { 'Content-Type': 'multipart/form-data' } };

                axios.post('/upload',this.data,config)
                    .then((response)=>{
                    console.log(response);
                })
                    .catch(error=>{
                        console.log(error);
                    })
                ;
            }
        },
        mounted() {

        }
    }
</script>
