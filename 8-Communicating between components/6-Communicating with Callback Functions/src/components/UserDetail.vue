<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User Name :  {{ switchName() }} </p>
        <button @click="resetName">Reset name</button>
        <button @click="resetFn">Reset name</button>
    </div>
</template>

<script>
  export default {
    props: {
        myName : {
            type : String
        },
        resetFn : Function
    },
    methods: {
        switchName() {
            return this.myName.split("").reverse().join("");
        },
        resetName () {
            this.myName = 'Pau'; //this works because is a object not a primitive and updates the reference
            this.$emit('nameWasReset', this.myName);
        }

    }
  }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
