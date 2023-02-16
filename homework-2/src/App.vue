<template>
  <div id="list-demo">
    <button @click="add" style="color: green">Add</button>
    <button @click="remove" style="color: red">Remove</button>
    <transition-group name="list" teg="ul">
      <li v-for="item in items" :key="item.id" class="list-item">
        🤔 {{ item + 1 }} - {{ item }} = ?
      </li>
    </transition-group>
  </div>
</template>
<script>
export default {
  data() {
    return {
      items: [1, 2, 3],
      nextNum: 10,
    };
  },
  methods: {
    randomItem() {
      return Math.floor(Math.random() * this.items.length);
    },
    add() {
      this.items.splice(this.randomItem(), 0, this.nextNum++);
    },
    remove() {
      this.items.splice(this.randomItem(), 1);
    },
  },
};
</script>
<style>
* {
  padding: 0;
  margin: 0;
}
body {
  margin-top: 50px;
  text-align: center;
  font-weight: bold;
}

button {
  padding: 5px 25px;
  margin: 0 0 20px 20px;
  font-weight: bold;
  border: 1px solid rebeccapurple;
  border-radius: 8px;
  background-color: #effea7;
  cursor: pointer;
}
.list-item {
  display: inline-block;
  justify-content: center;
  display: block;
}
</style>
