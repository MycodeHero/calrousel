<template>
    <div class="item">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: 'item',
    }
</script>
index
<style>
    .item{
        float:left;
        width:200px;
        height:267px;
        margin-left:5px;
    }
    .item img{
        width:100%;
    }
</style>