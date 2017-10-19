<template>
    <div class="component">
        <h3>You may edit the User here</h3>
        <p>Edit me!</p>
        <button @click = "editAge" > edit age </button>
        <!-- here i have a new click listener -->
        <p> Userage : {{userAge}} </p>
    </div>
</template>

<script>
export default {
props: ['userAge'],
methods: {
editAge() {
 this.userAge = 30;
 this.$emit('agewasedited', this.userAge);
}
}
}
</script>

<style scoped>
    div {
        background-color: lightgreen;
    }
</style>
