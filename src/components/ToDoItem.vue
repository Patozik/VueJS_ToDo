<template>

<div 
      class="item"
      v-bind:class="{ completed: item.completed }"
      v-bind:key="item.id">
      <h2>{{ item.title }}</h2>
      <button v-if="!item.completed" @click="removeItem">Zrobione</button>
      <button v-if="item.completed" @click="againItem">Nie zrobione</button>
</div>

</template>

<script>
export default {
    props: ['item'],
    methods: {
        removeItem() {
            this.$emit('removeClicked', this.item.id)
        },
        againItem() {
            this.$emit('againClicked', this.item.id)
        }
    }
}
</script>