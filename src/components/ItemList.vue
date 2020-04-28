<template>
    <div class="container">
        <ul class="list-group align-items-center" 
        v-for="(item, index) in itemsList" :key="item">
            <app-item :item="item" @click.native="deleteTheItem(index)"></app-item>
        </ul>
        <div class="row justify-content-start">
            <div class="col-2 counter">
            Number Of Items: {{numOfItems}}
            </div>
        </div>
    </div>
</template>

<script>
import Item from '../components/Item.vue';
export default {
    props:['itemsList', 'numOfItems'],
    components:{
        appItem: Item
    },
    data: function(){
        return{
            displayMessage:false
        }
    },
    methods:{
        deleteTheItem(index){
            this.$emit('deleteItem', index);
            if(this.numOfItems-1 === 0){
                alert('The cart is empty!')
            }
        }
    }
}
</script>


<style scoped>
.counter{
    font-size: 15px;
    text-align: center;
    border: 1px solid rgb(237, 235, 235);
    border-radius: 5%;
    margin-bottom: 5px;
}
</style>