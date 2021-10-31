<template>
    <div>
        <form>
            <input type="radio" name="radio-b" value="A" v-model="picked"/>
                <label>
                    <input type="date" id="date">
                </label><br>
            <input type="radio" name="radio-b"  value="B" v-model="picked" :id="repre"/>
                <label>
                    {{ repre }}
                </label>
            <template v-if="repreSelected" >
                <RepresentativeForm />
            </template>
        </form>
    </div>
</template>

<script>
import RepresentativeForm from "./RepresentativeForm.vue";

export default {
    name: "ThirdRadioButton",
    components: {
        RepresentativeForm,
    },
    data: () => ({
        picked: ""
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
input[type=date]{
    padding: 8px 16px;
    margin: 8px 0;
    box-sizing: border-box;
}
label {
  cursor: pointer;
}
</style>