<template>
       <div class="card">
           <div class="card-body item">
              <slot> </slot>
           </div>
       </div>
</template>

<script>
export default {
    name: 'Items',
}
</script>

<style>
    .card-body{
        font-family: 'Azizonia', cursive;
        font-size: 24px;
        color: #6e6e6e;
    }

    .item:hover{
        background-color: #ffe2e2;
    }
</style>