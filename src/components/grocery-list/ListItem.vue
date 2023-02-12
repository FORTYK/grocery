<template>
    <div class="grocery-list-item--wrapper">
        <div class="grocery-list-item">
            <span class="user--bullet" :style="[{backgroundColor: item.addedBy.color}]"></span>
            <span class="grocery-list-item--title ml-2">
                {{item.title}}
            </span>
        </div>
        <button @click="remove" class="btn btn-cross border rounded-l-none border-l-0">
        <span class="cross"></span>
        </button>
    </div>
</template>

<script>
export default {
    emit: ['remove-item'],
    props: ['item'],
    methods: {
        remove(){
            this.$emit('remove-item', this.item);
        }
    }
}
</script>

<style scoped>
.grocery-list-item--wrapper{
    @apply flex flex-row items-stretch mt-2;
}

.grocery-list-item--wrapper > div{
    
}

.grocery-list-item--wrapper > div:first-child{
    @apply flex-grow border rounded-l;
}

.grocery-list-item--wrapper > div:last-child{
    @apply rounded-r text-center;
    width: 40px;
}
.btn-cross:hover{
    @apply bg-red-600 text-white;
}
.grocery-list-item{
    @apply flex flex-row px-3 py-2;
}
</style>