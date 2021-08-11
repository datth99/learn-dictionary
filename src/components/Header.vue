<template>
    <div>
        <h3>Số lượng</h3>
        <div class="progress mb-3">
            <div class="progress-bar" role="progressbar" :style="{width: (itemCount / itemMax) * 100 + '%'}" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100"></div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['itemCount', 'itemMax'],
}
</script>

<style lang="">
    
</style>