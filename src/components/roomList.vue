<template>
  <ul class="room-list">
        <li v-for="(roomitem, i) in roomItems" :key="i" class="room-item">
            <router-link to="/room">
                <span class="room-num">{{roomitem.num | formatRoomNum}}</span>
                <span class="room-tit">{{roomitem.tit}}</span>
                <span class="room-own">{{roomitem.own}}</span>
                <span class="room-user">
                    <span class="room-user-num">{{roomitem.userNowNum}}</span>/{{roomitem.userNum}}
                </span>
            </router-link>
        </li>
    </ul>  
</template>

<script>
export default {
    name: 'roomList',
    data() {
        return {
            roomItems: this.$store.state.roomDTO
        }
    },
    filters: {
        formatRoomNum(num) {
            return String(num).padStart(3, 0)
        }
    }
}
</script>