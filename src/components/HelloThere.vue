<script>
export default {
    data() {
        return {
            randomColor: "blue",
            borderStyle: "2px solid red",
            buttonFontSize: "2",
        };
    },
    methods: {
        getRandomColor() {
            return "#" + (((1 << 24) * Math.random()) | 0).toString(16);
        },
        getRandomNumber() {
            return Math.floor(Math.random() * 10) + 1;
        },
        pickStyle() {
            this.randomColor = this.getRandomColor();
            this.borderStyle =
                this.getRandomNumber() + "px solid " + this.getRandomColor();
            this.buttonFontSize = this.getRandomNumber();
        },
    },
};
</script>

<template>
    <h1 class="text">Hi There!</h1>
    <button class="btn" @click="pickStyle">Random color</button>
</template>

<style scoped>
.text {
    color: v-bind(randomColor);
    border: v-bind(borderStyle);
    padding: 20px;
}
.btn {
    cursor: pointer;
    font-size: calc(v-bind(buttonFontSize + "px") * 10);
}
</style>
