<template>
    <div class="group-list">
        <groupItem v-for="(n, i) in 1" :key="i"/>
    </div>
</template>

<script>
import groupItem from '@/components/groupItem.vue'

export default {
    name: 'groupList',
    components: {
        groupItem
    },
    data() {
        return {
            groupDTO: this.$store.state.groupDTO
        }
    }
}
</script>