<template>
    <div>
        <h4 class="group-tit" :class="{off : !active}">
            <a href="#" @click.prevent="!active">User</a>
        </h4>
        <ul class="user-list" v-show="active">
            <userItem v-for="(useritem, i) in userList" :key="i"/>
        </ul>
    </div>
</template>

<script>
import userItem from '@/components/userItem.vue'

export default {
    name: 'groupItem',
    components: {
        userItem
    },
    data() {
         return {
             active: false,
             userList : this.$parent.groupDTO
         }
     }
}
</script>