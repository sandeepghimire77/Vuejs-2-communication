<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p> User name : {{myName}} </p>
         <button @click="resetName">Reset Name</button>

         <button @click="resetFn()">Reset Name</button>
         <p> Userage : {{userAge}} </p>
    </div>
</template>

<script>
export default {
props: {
            myName: {
                type: String,
                required: true
            },
            resetFn: Function,
            userAge: Number

},
methods: {

            resetName() {
                this.myName = 'sandeep';
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
