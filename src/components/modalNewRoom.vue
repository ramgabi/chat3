<template>
    <div class="modal-basic">
            <h4 class="modal-tit">NEW ROOM</h4>
            <div class="modal-frm">
                <input 
                    type="text" 
                    placeholder="방 이름을 입력해주세요" 
                    v-model="roomName"
                    title="방 이름 입력" 
                    class="modal-room-name-input"
                >
                <div class="modal-room-member-wrap">
                    <input 
                        type="number" 
                        @keyup="checkNum"
                        v-model="roomUserCount"
                        min="2" 
                        max="99" 
                        title="방 인원 입력" 
                        class="modal-room-user-input"
                    >
                    <div class="modal-bnt-wrap">
                        <button 
                            @click.prevent="roomUserCount--"
                            class="btn-basic btn-count"
                        >-</button>
                        <button  
                            @click.prevent="roomUserCount++"
                            class="btn-basic btn-count"
                        >+</button>
                    </div>
                </div>
                <div class="modal-bnt-wrap">
                    <button 
                        @click.prevent="createRoom"
                        class="btn-basic bg-purple"
                    >CREATE</button>
                    <button 
                        @click.prevent="resetNewRoomModal"
                        class="btn-basic bg-grey"
                    >CANCEL</button>
                </div>
            </div>
        </div>
</template>

<script>
export default {
    name: 'modalNewRoom',
    components: {

    },
    data() {
      return {
        roomName : null,
        roomUserCount: 1,
        roomItems: this.$store.state.roomDTO,
        showModal: this.$store.state.showModal
      }
    },
    methods: {
        checkNum() {

        },
        modalOff() {
            this.$store.state.showModal = false
        },
        createRoom() {
            const newRoom = {
                num : this.roomItems.length + 1,
                tit : this.roomName,
                own : this.$store.state.userDTO.name,
                userNowNum : 0,
                userNum : this.roomUserCount
            }
            this.$store.state.roomDTO.push(newRoom)
            this.resetNewRoomModal()
        },
        resetNewRoomModal() {
            this.roomName = null
            this.roomUserCount = 1

            this.modalOff()
        }
    }
}
</script>