<template>
  <div>
    <module-window
      v-if="modWindow"
      v-model="modWindow"
      v-model:oth="mainWindow"
    ></module-window>

    <div v-if="mainWindow" class="a">
      <div class="enter">
        <div
          class="enterLink"
          style="cursor: pointer"
          @click="
            modWindow = true;
            mainWindow = false;
          "
        >
          Войти
        </div>
        <svg
          style="cursor: pointer"
          @click="
            modWindow = true;
            mainWindow = false;
          "
          width="22"
          height="22"
          viewBox="0 0 22 22"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M8 20H4C3.46957 20 2.96086 19.7893 2.58579 19.4142C2.21071 19.0391 2 18.5304 2 18V4C2 3.46957 2.21071 2.96086 2.58579 2.58579C2.96086 2.21071 3.46957 2 4 2H8"
            stroke="#41522E"
            stroke-width="2.2"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M15 16L20 11L15 6"
            stroke="#41522E"
            stroke-width="2.2"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <path
            d="M20 11H8"
            stroke="#41522E"
            stroke-width="2.2"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </div>
      <div class="c">
        <div class="l">
          <left-up></left-up>
          <left-down :favoritesComp="favorites"></left-down>
        </div>
        <right-center
          :hotelsComp="hotels"
          :favoritesComp="favorites"
          @changeLike="addFavorites"
        ></right-center>
      </div>
    </div>
  </div>
</template>

<script>
import ModuleWindow from "@/components/ModuleWindow.vue";
import LeftUp from "./components/LeftUp.vue";
import LeftDown from "./components/LeftDown.vue";
import RightCenter from "./components/RightCenter.vue";
export default {
  components: { ModuleWindow, LeftUp, LeftDown, RightCenter },
  data() {
    return {
      hotels: [],
      modWindow: false,
      mainWindow: true,
      favorites: [],
    };
  },
  methods: {
    addFavorites(el) {
      if (this.hotels[el] == "NOTshow") {
        this.hotels[el] = "show";
        this.favorites.push(el);
      } else {
        this.hotels[el] = "NOTshow";
        this.favorites.splice(0, 1);
      }
      console.log(this.favorites);
    },
    formArrayHotels() {
      for (let i = 0; i < 100; i++) {
        this.hotels.push("NOTshow");
      }
    },
  },
  mounted() {
    this.formArrayHotels();
  },
};
</script>

<style>
button {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 7px;
  gap: 10px;
  width: 296px;
  height: 50px;
  background: linear-gradient(104.34deg, #41522e -15.34%, #be8022 145.95%);
  box-shadow: 0px 0px 2px rgba(0, 0, 0, 0.15);
  border-radius: 4px;
  flex: none;
  order: 1;
  align-self: stretch;
  flex-grow: 0;
}
button:hover {
  background: linear-gradient(
      0deg,
      rgba(255, 255, 255, 0.2),
      rgba(255, 255, 255, 0.2)
    ),
    linear-gradient(104.34deg, #41522e -15.34%, #be8022 145.95%);
  border-radius: 4px;
}
button:active {
  background: linear-gradient(0deg, rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.2)),
    linear-gradient(104.34deg, #41522e -15.34%, #be8022 145.95%);
  border-radius: 4px;
}
.a {
  background-color: rgb(241, 241, 241);
  min-height: 100vh;
  display: flex;
  padding: 30px;

  flex-direction: column;
  align-items: center;
}
.enter {
  background-color: rgb(241, 241, 241);
  display: flex;
  height: 79px;
  width: 90%;
  justify-content: flex-end;
  align-items: center;
}
.enterLink:hover {
  text-decoration: underline;
}
.c {
  background-color: rgb(241, 241, 241);
  min-height: 100vh;
  display: flex;
  justify-content: center;
  padding: 30px;
  width: 80%;
}
.l {
  background-color: rgb(241, 241, 241);
  min-height: 100vh;
  display: flex;
  min-width: 190px;
  width: 30%;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}
.imagineScroll {
  display: flex;
  overflow-x: auto;
}
.price {
  display: flex;
  width: 101px;
  justify-content: space-between;
}
.priceWord {
  color: rgb(186, 183, 183);
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  font-size: 14px;
}
.priceAndLike {
  display: flex;
  align-items: flex-end;
  flex-direction: column;
  justify-content: space-evenly;
  width: 10px;
}
</style>
