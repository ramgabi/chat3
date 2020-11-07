<template>
    <ul class="menu-list">
        <li v-for="(menuItem, i) in menuItems" :key="i" class="menu-item">
            <a :href="menuItem.href" :class="menuItem.name">
                <h2>{{menuItem.name}}</h2>
            </a>
        </li>
        <!-- <li class="menu-item"><a href="#" class="home"><h2>홈</h2></a></li>
        <li class="menu-item"><a href="#" class="board"><h2>게시판</h2></a></li>
        <li class="menu-item"><a href="#" class="chat on"><h2>채팅</h2></a></li>
        <li class="menu-item"><a href="#" class="set"><h2>설정</h2></a></li> -->
    </ul>
</template>

<script>
export default {
    name: 'menu-list',
    data() {
        return {
            menuItems: [
                {
                    name: 'home',
                    href: ''
                },
                {
                    name: 'board',
                    href: ''
                },
                {
                    name: 'chat',
                    href: ''
                },
                {
                    name: 'set',
                    href: ''
                }
            ]
        }
    }
}
</script>