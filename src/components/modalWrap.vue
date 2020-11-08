<template>
    <div 
        v-if="$store.state.showModal"
        @click.self="modalOff()"
        class="modal-wrap"
    >
        <modalNewRoom/>
    </div>
</template>

<script>
import modalNewRoom from '@/components/modalNewRoom.vue'

export default {
    name: 'modalWrap',
    components: {
        modalNewRoom
    },
    data() {
        return {
            
        }
    },
    methods: {
        modalOff() {
            this.$store.state.showModal = false
        }
    }
}
</script>