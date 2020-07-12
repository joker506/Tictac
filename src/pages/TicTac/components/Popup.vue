<template>
  <div class="wrapp">
    <div class="popup">
      <h2 class="popup-title">Win {{this.activePlayer}}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: "Popup",
  props: ["activePlayer"]
};
</script>

<style scoped >
.wrapp {
  width: 300px;
  background-color: rgb(115, 174, 182);
  border: 3px solid rgb(94, 134, 139);
  border-radius: 5px;
}
</style>