<template>
  <div>
    <div class="item" @click="move" v-bind:class="{active:freeze}">{{mark}}</div>
  </div>
</template>

<script>
export default {
  name: "TicTac",
  props: ["name"],
  data() {
    return {
      freeze: false,
      mark: "",
      count: 0
    };
  },
  methods: {
    move() {
      this.mark = this.$parent.activePlayer;
      this.freeze = true;
      this.$emit("changeActive", this.name);
    }
  }
};
</script>

<style scoped >
.item {
  width: 50px;
  height: 50px;
  margin-top: 10px;
  background-color: rgb(83, 125, 150);
  border: 1px solid #345b72;
  cursor: pointer;
  box-sizing: border-box;
  padding-top: 10px;
}

.active {
  box-sizing: border-box;
  border: 3px solid aqua;
}
</style>