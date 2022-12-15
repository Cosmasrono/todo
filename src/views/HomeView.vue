<template>
  <main class="">
  <div>
    <h1 class="flex justify-center items-center text-3xl">Take Away notebook</h1>
    <p class="flex justify-center items-center mt-4">hello everyone here is ther platform to record your diary</p>
    <form @submit.prevent="addItem" class="flex flex-col justify-center items-center">
      <h1 class="text-3xl">add your diary</h1>
      <input type="text" v-model="newItem" class="p-7 mt-3 text-black bg-green-400" placeholder="Add a new diary" required/>
      <button class="p-5 mt-10 bg-green-400 rounded-lg">Add your diary</button>
    </form>
    <ul>
      <li v-for="(item, index) in items" :key="index">
        {{ item }}
         
        <button @click="updateItem(index)" class=" items-center justify-start p-5 m-4 bg-green-400 rounded-lg">Edit</button>
        <button @click="deleteItem(index)" class=" items-center justify-start p-5 bg-green-400 rounded-lg">Delete</button>
       
      </li>
    </ul>
  </div>

<footer class="p-4 bg-white rounded-lg shadow md:flex md:items-center md:justify-between md:p-6 dark:bg-gray-800">
    <span class="text-sm text-gray-500 sm:text-center dark:text-gray-400 justify-center"><span class=" text-green-500">© cossing wing001@2022</span> . All Rights Reserved.
    </span>
     
</footer>

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
      this.newItem = '',
      localStorage.setItem('items', JSON.stringify(this.items));
    },
    updateItem(index) {
      this.items[index] = prompt('Update item:', this.items[index])
    },
    deleteItem(index) {
      this.items.splice(index, 1)
      console.log(index);
    }
  },
  mounted() {
    const storedTodos= localStorage.getItem('items');
    if (storedTodos) {
      this.items = JSON.parse(storedTodos);
    }
  }
}
</script>

