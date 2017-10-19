<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User! : name is : {{names}}</p>

        <button @click= 'changename' > change name </button>

        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <app-user-detail :myName = 'names'  @nameWasReset="names = $event"
                 :resetFn="resetName"
                 :userAge="age"></app-user-detail>
                <!-- just by binding name ' :name ' we pass the data from parent component to the child components -->
            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit :userAge= "age"
                @agewasedited = "age = $event" ></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
    import UserDetail from './UserDetail.vue';
    import UserEdit from './UserEdit.vue';

    export default {
    data: function() {
    return {
    names: 'sandeep',
    age : 27
    };
    },
    methods: {
    changename() {
    this.names = 'akshar'
    },
     resetName() {
      this.names = 'sandeep';
                }
    },
        components: {
            appUserDetail: UserDetail,
            appUserEdit: UserEdit
        }
    }
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>
