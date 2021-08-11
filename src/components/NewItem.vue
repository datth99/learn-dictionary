<template>
   <div class="row">
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-md-6 col-sm-offset-3 form-group">
                <label for=""><b>Thêm mới</b></label>
                <textarea class="form-group" name="" id="" cols="30" rows="10" v-model="item"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset-2 col-md-6 col-sm-offset-3 form-group">
                <button class="btn btn-success" @click.prevent="createNew">Thêm</button>
            </div>
        </form>
   </div>
</template>

<script>
export default {
    data(){
        return {
            item: ''
        }
    },
    methods: {
        createNew(){
            if(this.item == ''){
                return false;
            }else{
                this.$emit('saveItem', this.item);
                this.item = '';
            }
        }
    },
}
</script>

<style>
    
</style>