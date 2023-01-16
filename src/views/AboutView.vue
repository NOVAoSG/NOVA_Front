<template>
  <div class="about">
    <ul>
    <h1>What Do you Want?</h1>

    
      <ListItem v-for="(item, i) in listItems" :key="i" :content="item" @delete="deleteItem(i)" />
    </ul>
    <input type="text" name="list-new-item" id="" v-model="newItem">
    <button @click="addNewItem" >Add</button>

  </div>
</template>

<script>

import ListItem from "@/components/ListItem.vue"
export default {
  components: { ListItem },
  data() {
    return {
      listItems: [
        "MakeKeyBoard",
        "Journey",
        "MAKE GOOD",
        "JKL"
      ],
      newItem: ""
    }
  },
  methods: {
    addNewItem() {
      this.listItems.push(this.newItem)
      this.newItem = ""
    },
    deleteItem(index) {
      this.listItems.splice(index, 1);
    }
  }
}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
