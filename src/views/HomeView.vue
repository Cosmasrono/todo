<template>
  <main class="">
  <div>
    <h1 class="flex justify-center items-center text-6xl">Todo list</h1>
    <form @submit.prevent="addItem" class="flex flex-col justify-center items-center">
      <h1 class="text-3xl">add your diary</h1>
      <input type="text" v-model="newItem" placeholder="Add a new item" required/>
      <button class="p-5 bg-green-400 rounded-lg">Add your diary</button>
    </form>
    <ul>
      <li v-for="(item, index) in items" :key="index">
        {{ item }}
        <div class="">
        <button @click="updateItem(index)" class="gap-4 p-5 bg-green-400 rounded-lg">Edit</button>
        <button @click="deleteItem(index)" class="gap-4 p-5 bg-green-400 rounded-lg">Delete</button>
      </div>
      </li>
    </ul>
  </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      newItem: '',
      items: []
    }
  },
  methods: {
    addItem() {
      this.items.push(this.newItem)
      this.newItem = ''
    },
    updateItem(index) {
      this.items[index] = prompt('Update item:', this.items[index])
    },
    deleteItem(index) {
      this.items.splice(index, 1)
    }
  }
}
</script>

