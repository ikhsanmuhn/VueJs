<template>
  <div id="app">
    <BaseRadioButtonGroup :options="decisions" v-model="selected" />
    <div class="input-group">
      <row>
        <h5 style="margin: 0px">Subcomponent</h5>
      </row>
      <row>
        <template v-if="radioASelected">
          <SecRadioButton :repre="represent" />
        </template>
        <template v-else-if="radioBSelected">
          <ThirdRadioButton :repre="represent" />
        </template>
        <template v-else-if="radioCSelected">
          <FourthRadioButton :repre="represent" />
        </template>
      </row>
    </div>
  </div>
</template>

<script>
import BaseRadioButtonGroup from "./components/BaseRadioButtonGroup";
import SecRadioButton from "./components/SecRadioButton.vue";
import ThirdRadioButton from "./components/ThirdRadioButton.vue";
import FourthRadioButton from "./components/FourthRadioButton.vue";

export default {
  name: "App",
  components: {
    BaseRadioButtonGroup,
    SecRadioButton,
    ThirdRadioButton,
    FourthRadioButton
  },
  data: () => ({
    decisions: ["Radio A", "Radio B", "Radio C"],
    represent: "Representative Form",
    selected: "",
  }),
  computed: {
    radioASelected() {
      return this.selected === "Radio A";
    },
    radioBSelected() {
      return this.selected === "Radio B";
    },
    radioCSelected() {
      return this.selected === "Radio C";
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.input-group {
  width: 35%;
  margin: 20px auto;
  padding: 15px 20px;
  border-radius: 8px;
  background-color: #ebebeb94;
}

span {
  font-size: 25px;
}
</style>
