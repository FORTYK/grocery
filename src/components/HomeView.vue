<template>
    <div>
        <div class="mt-11 grocery">
            <UserList @set-user="setUser"/>
            <div class="grocery--form">
                <AddForm @add-item="addItem"/>
                <hr class="my-5">
                <GroceryList :list="list" @update-list="setList"/>
            </div>
        </div>
    </div>
</template>
<script>
import AddForm from "./grocery-list/AddForm.vue";
import GroceryList from "./grocery-list/GroceryList.vue";
import UserList from "./user-list/UserList.vue";

var id=0;
export default {
    data() {
        return {
            user: {
                id: 1, 
                color: '#3bafda',
                name: 'Linnea'
            },
            list: [{id: id++, addedBy: {
                id: 1, 
                color: '#3bafda',
                name: 'Linnea'
            }, title: 'Milk'}],
        }
    },
    methods: {
        setUser(user) {
            this.user = user;
        },
        addItem(item){
            this.list.push({id: id++, addedBy: this.user, title: item});
        },
        setList(list){
            this.list = list;
        }
    },
    components: {
        AddForm,
        GroceryList,
        UserList,
    }
}
</script>

<style scoped>
.grocery--form{
    @apply flex-grow flex-col;
}

.grocery{
    @apply flex flex-row;
}

</style>>