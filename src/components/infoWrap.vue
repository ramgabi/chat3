<template>
    <section class="info-wrap">
        <h3 class="info-tab">
            Online
            <span class="info-user-num">99</span> <!-- DTO.length로 숫자 input -->
        </h3>
        <groupList v-for="(n, i) in 3" :key="i"/> <!-- 임시로 v-for -->
        <userProfile/>
    </section>
</template>

<script>
import userProfile from '@/components/userProfile.vue'
import groupList from '@/components/groupList.vue'

export default {
    name: 'infoWrap',
    components: {
        userProfile,
        groupList
    },
    data() {
        return {
            // DTO 받아서 하위로도 넘기기
        }
    }
}
</script>