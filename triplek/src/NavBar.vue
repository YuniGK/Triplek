<template>
  <nav class="navbar navbar-expend-lg navbar-dark bg-dark">
    <div class="container-fluid">
        <a href="/" class="navbar-brand">Triplek</a>

        <button class="navbar-boggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarNav">
            <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarNav">
            <ul :class="{'navbar-nav':true, 'me-auto':menu.me_auto}"
                v-for="menu in menu_category" :key="menu.id">
                <li class="nav-item" v-for="menu_object in menu.value" :key="menu_object.key">
                    <a :class="{'nav-link':true, active: menu == menu_object.key}"
                        @click="onMovePage($event, menu_object)"
                        href="#">
                        {{menu_object.value}}
                    </a>
                </li>
            </ul>
        </div>
    </div>
  </nav>
</template>

<script>
import {ref, computed} from 'vue'

export default {
    name: 'NavBar',
    setup(){
        const menu = ref('home')

        const menus = [
            {key: 'home', value : '홈', URL: '#', position: 'left'},
            {key: 'app', value : '애플리케이션', URL: '#', position: 'left'},
            {key: 'me', value : '프로필', URL: '#', position: 'right'},
        ]
    }
}
</script>

<style>

</style>