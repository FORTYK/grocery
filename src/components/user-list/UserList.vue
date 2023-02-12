<template lang="">
    <div class="users-list--wrapper">
        <h2>Users</h2>
        <div class="users-list--list">
            <div  @click="select(user)" class="users-list--user" :class="[{active: user.id === selected}]" v-for="(user) in users" :key="user.id">
                <span class="user--bullet" :style="[{backgroundColor: user.color}]">

                </span>
                <span class="user--name">
                    {{user.name}}
                </span>
            </div>
        </div>
    </div>
</template>
<script>
var id = 0;
export default {
    data() {
        return {
            users: [{
                id: id++, 
                color: '#ff6f61',
                name: 'Christian'
            }, {
                id: id++, 
                color: '#3bafda',
                name: 'Linnea'
            }],
            selected: 1,
            selectedClass: 'active'
        }
    },
    methods: {
        select(user){
            this.selected = user.id;
            this.$emit('set-user', user);
        }
    }
}
</script>
<style scoped>
.users-list--wrapper{
    @apply pr-5;
    width: 300px;
}

.users-list--user{
    @apply flex flex-row rounded px-3 py-2 border mb-2 text-gray-500 text-lg;
}

.active{
    @apply border-gray-600 text-gray-800;
}

.users-list--user:hover {
    @apply border-black;
}

.users-list--user:hover .user--name{
    @apply text-black;
}

.user--name{
    @apply ml-2;
}

</style>