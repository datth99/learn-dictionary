<template>
  <div id="app" class="mt-2">
      <div class="container">
        <app-header :itemCount="items.length" :itemMax="itemMax"></app-header>
        <div class="row">
          <div class="col-sm-12" v-if="isAlert">
            <div class="alert alert-success" role="alert">
              {{messages}}
            </div>
          </div>
        </div>
        <div class="row">
          <div class="col-sm-12">
            <app-new-item @saveItem="createNew"></app-new-item>
          <app-item-layout :items="items" @removeItem="removeItem"></app-item-layout>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import NewItem from './components/NewItem.vue'
import ItemLayout from './components/ItemLayout.vue'
export default {
  name: 'App',
  data(){
    return {
      items: [
        'I love U',
        'You can say hello',
      ], 
      itemMax: 8,
      isAlert: false,
      messages: ''
    }
  },
  components: {
    appItemLayout: ItemLayout,
    appNewItem: NewItem,
    appHeader: Header
  },
  methods: {
    createNew(item){
      if( this.items.length > this.itemMax){
        this.messages = "Từ mới đã đầy! Vui lòng xóa item!";
      }else{
        this.items.push(item);
        this.isAlert = true;
        this.messages = "Thêm từ mới thành công!";
      }
    },
    removeItem(index){
      this.items.splice(index, 1);
      this.isAlert = true,
      this.messages = "Xóa từ mới thành công!"
    }
  },

}
</script>

<style>

</style>
