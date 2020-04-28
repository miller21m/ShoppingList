<template>
<div class="row list-group-item list-group-item-primary col-md-4 text">
    <slot>{{item}}</slot>
</div>    
</template>

<script>
export default {
    props:['item']
}
</script>

<style scoped>
.text{
    text-align: center;
}
</style>