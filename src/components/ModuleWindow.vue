<template>
  <div>
    <div class="modWindowClass" @click="change">
      <div class="inputModWindowClass" @click.stop>
        <h2>Simple Hotel Check</h2>
        <div
          style="display: flex; align-content: center; flex-direction: column"
        >
          <div>Логин</div>
          <input style="height: 30px" type="text" />
        </div>
        <div
          style="display: flex; align-content: center; flex-direction: column"
        >
          <div>Пароль</div>
          <input style="height: 30px" type="text" />
        </div>
        <button>Войти</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    change() {
      this.$emit("update:modelValue", false);
      this.$emit("update:oth", true);
    },
  },
};
</script>

<style scoped>
.modWindowClass {
  display: flex;
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  position: fixed;
  background-image: url(@/assets/IMG_20210312_140957_1741.png);
  background-repeat: no-repeat;
  background-size: 100% 100%;
  backdrop-filter: url(@/assets/IMG_20210312_140957_1741.png);
  backdrop-filter: blur(10px);
  z-index: 0;
}
.inputModWindowClass {
  display: flex;
  min-width: 409px;
  min-height: 382px;
  background-color: white;
  margin: auto;
  border-radius: 20px;
  justify-content: space-around;
  align-content: center;
  flex-wrap: wrap;
  flex-direction: column;
  z-index: 1;
}
</style>
