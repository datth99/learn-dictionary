<template>
    <div class="row">
       <app-item v-for="(item, index) in items" :key="item" v-bind:data="item" @click.native="removeItem(index)">{{item}}</app-item>
    </div>
</template>

<script>
import Items from './Items.vue'
export default {
    name: 'ItemLayout',
    props: ['items'],
    components: {
        appItem: Items
    },
    methods: {
        removeItem(index){
            this.$emit('removeItem', index)
        }
    },
}
</script>

<style scoped>
    
</style>