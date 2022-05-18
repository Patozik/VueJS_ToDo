<template>
  <div>
    <div class="item">
        <input type="text" placeholder="Zadanie" v-model="newItem">
        <button @click="addItem">Dodaj</button>
    </div>

    <ToDoItem  
        v-for="item in items"
        v-bind:key="item.id" 
        v-bind:item="item"
        @removeClicked="removeItem"
        @againClicked="againItem"
    />

 </div>
</template>

<script>
import ToDoItem from './ToDoItem.vue'
export default {
    components: {
        ToDoItem
    },
    data() {
        return {
        newItem: '',
        items: [
            {title: 'Stworzyć program', completed: false, id: 'aa1'},
            {title: 'Spotkać się z znajomymi', completed: true, id: 'ab1'}
        ]
        }
    },
    methods: {
        addItem() {
        this.items.push({ 
        title: this.newItem, 
        completed: false, 
        id: Math.random()
        })
        this.newItem = ''
        },
        removeItem(id){
        const index = this.items.findIndex(el => el.id === id)
        this.items[index].completed = true
        }, 
        againItem(id){
        const index = this.items.findIndex(el => el.id === id)
        this.items[index].completed = false
        } 

  }
}
</script>

<style>

input{
  margin: 8px;
  padding: 10px;
  font-family: myFont;
}

button{
  border: 1px solid #cdcdcd;
  background-color: #5fe6f5;
  margin: 8px;
  padding: 10px;
  font-family: myFont;
}

.item{
  border: 1px solid #cdcdcd;
  background-color: #5fe6f5;
  margin: 8px;
  padding: 10px;
}

.completed{
  opacity: 0.5;
}

.completed h2 {
  text-decoration: line-through;
}
</style>
