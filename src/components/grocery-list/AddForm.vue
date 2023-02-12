<template lang="">
    <div class="grocery--form-add">
        <h2>Add a new item</h2>
        <form class="grocery--form-add--form" @submit.prevent=add>
            <input class="grocery--form-add--input" type="text" v-model="newItem">
            <button class="btn btn-submit grocery--form-add--submit" type="submit">+</button>
        </form>      
    </div>
</template>
<script>
export default {
    data(){
        return {
            newItem: ''
        }
    },
    methods: {
        add(){
            this.$emit('add-item', this.newItem);
            this.newItem = '';
        }
    }
}
</script>

<style scoped>

.grocery--form-add{
    @apply flex-grow flex-col;
}

.grocery--form-add--form{
    @apply flex;
}

.grocery--form-add--input{
    @apply flex-grow rounded-r-none border border-r-0 border rounded px-3 py-3;
}

.grocery--form-add--submit{
    @apply border-l-0 rounded-l-none bg-green-400 text-white text-xl font-bold px-11 py-3;
}

</style>