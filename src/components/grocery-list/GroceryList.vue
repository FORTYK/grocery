<template lang="">
    <div class="grocery-list--wrapper">
        <div class="grocery-list" v-for="item in list" :key="item.id">
            <ListItem @remove-item="removeItem" :item="item" />
        </div>
    </div>
</template>
<script>
import ListItem from "./ListItem.vue";

export default{
    props: ['list'],
    emits: ['update:list'],
    components: {
        ListItem
    },
    methods: {
        removeItem(item) {
            this.$emit('update-list', this.list.filter(i => i.id !== item.id));
        }
    }
}
</script>
<style scoped>
.grocery-list--wrapper { 
    @apply mt-5;
}
.grocery-list{

}
</style>