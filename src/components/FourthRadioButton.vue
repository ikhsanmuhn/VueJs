<template>
    <div>
        <input type="radio" name="radio-a" value="A" v-model="picked"/>
            <label>
                <input type="text" id="text"  placeholder="Hey!" >
            </label><br>
            <div style="display: flex; align-items:center;">
                <input type="radio" name="radio-a" value="B" v-model="picked" :id="repre"/>
                <RepresentativeForm />
            </div>
    </div>
</template>

<script>
import RepresentativeForm from "./RepresentativeForm.vue";

export default {
    name: "FourthRadioButton",
    components: {
        RepresentativeForm,
    },
    data: () => ({
        picked: "",
    }),
    props: {
        repre: {
        required: true,
        type: String,
        },
    },
    computed: {
        repreSelected() {
            return this.picked === "B";
        },
    }
};
</script>

<style scoped>
input[type=radio]{
    margin-right: 10px;
    margin-bottom: 20px;
}
input[type=text]{
    padding: 8px 16px;
    margin: 8px 0;
    box-sizing: border-box;
}
label {
  cursor: pointer;
}
</style>