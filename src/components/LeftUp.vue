<template>
  <div class="lu">
    <div style="width: 80%">
      <label
        >Локация
        <input style="width: 100%; height: 30px" value="Москва" type="text"
      /></label>
    </div>
    <div style="width: 81%">
      <label
        >Дата заезда <input style="width: 100%; height: 40px" type="date"
      /></label>
    </div>
    <div style="width: 80%">
      <label
        >Колличество дней
        <input
          style="width: 100%; height: 30px"
          min="1"
          value="1"
          type="number"
      /></label>
    </div>
    <div style="width: 82%">
      <button style="width: 100%; height: 35px">Найти</button>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.lu {
  background-color: white;
  min-height: 49%;
  display: flex;
  width: 100%;
  border-radius: 20px;
  min-width: 240px;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
}
</style>
