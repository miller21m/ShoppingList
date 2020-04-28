<template>
    <div class="row content align-items-center">
            <h3 class="title">MY SHOPPING LIST</h3>
            <div class="input-group mb-3">

            <input type="text"
            class="form-control"
            placeholder="Enter your Item"
             aria-describedby="basic-addon1"
             v-model="item">
             <button @click="addItemToList">ADD ITEM</button>
            </div>
    </div>
</template>

<script>
export default {
    data: function(){
        return{
           item:'' 
        }
    },
    methods:{
        addItemToList(){
            if(this.item===''){
                alert('Empty item please enter somthing!');
                return;
            }
            this.$emit('addItem', this.item);
            this.item='';
        }
    }
}
</script>

<style scoped>
    .content{
        display: block;
        text-align: center;
    }

    .title{
        
    }
</style>