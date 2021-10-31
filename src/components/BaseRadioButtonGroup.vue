<template>
  <div class="radio-group">
    <div class="input-group" style="text-align: center;">
      <row>
        <h5 style="margin: 0px">Name</h5>
      </row>
      <row>
        <FirstRadioButton v-for="option in options" :option="option" :key="option" />
      </row>
    </div>
  </div>
</template>

<script>
import FirstRadioButton from "./FirstRadioButton.vue";

export default {
  name: "BaseRadionButtonGroup",
  components: {
    FirstRadioButton,
  },
  props: {
    options: {
      required: true,
      type: Array,
    },
  },
};
</script>

<style scoped>
.input-group {
  width: 35%;
  margin: 20px auto;
  padding: 15px 20px;
  border-radius: 8px;
  background-color: #ebebeb94;
}

label {
  cursor: pointer;
}
</style>