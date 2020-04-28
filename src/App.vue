<template>
  <div class="container">
    <app-header @addItem="newItemToAdd"></app-header>
    <app-item-list 
    :itemsList="listOfItems" 
    :numOfItems="listOfItems.length"
    @deleteItem="itemTodelete"></app-item-list>

    <div class="alert alert-info">
      INFO: Click on the ITEM in order to Delelte it! 
    </div>    
  </div>
</template>

<script>
import ItemList from './components/ItemList.vue';
import Header from './components/Header.vue';
export default {
  data: function(){
    return{
    listOfItems:[
      'Milk',
      'Bred'
    ],
    numOfItems:0
    }
  },
  components:{
    appItemList: ItemList,
    appHeader: Header
  },
  methods:{
    newItemToAdd(item){
      this.listOfItems.push(item);
    },
    itemTodelete(index){
      this.listOfItems.splice(index,1);
    }
  }
}
</script>

<style scoped>

</style>