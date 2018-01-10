<template>
    <div class="container">
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <div class="panel panel-default">
                    <div class="panel-heading">VUe Example Component</div>

                    <div class="panel-body">

                        <form>
                            <legend>Upload form</legend>

                            <div class="form-group">
                                <label>Upload Files</label>
                                <input type="file" multiple class="form-control">
                            </div>




                            <button type="submit" class="btn btn-primary">Submit</button>
                        </form>

                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
