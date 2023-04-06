<template>
    <header>
        <div class="header-wrap">
            <h2 class="logo">Aleksandr</h2>
            <nav ref="menu"
             class="nav-wrap">
                <ul class="nav-links">
                    <li v-for="link in menuLinks"
                     :key="link.name"
                     class="nav-link">
                        <router-link @click="toggleMenu"
                         :to="link.link">
                            {{ link.name }}
                        </router-link>
                    </li>
                </ul>
            </nav>

            <button @click="toggleMenu"
             class="menu-btn-wrap">
                <img class="menu-btn-pic"
                 :src="listDash"
                 alt="menu">
            </button>
        </div>
    </header>
</template>
<script>
import listDash from '@/assets/svg/list.dash.svg'

export default {
    name: 'HeaderComp',
    data() {
        return {
            listDash,
            menuLinks: [
                {
                    name: 'Main',
                    link: '/'
                },
                {
                    name: 'About',
                    link: '/about'
                },
                {
                    name: 'Projects',
                    link: '/projects'
                },
                {
                    name: 'Contact',
                    link: '/contact'
                },
            ]
        }
    },
    methods: {
        toggleMenu() {
            const navLinks = this.$refs.menu
            const body = document.body
            body.classList.toggle('no-scroll')
            navLinks.classList.toggle('menu-active')
        }
    },
}
</script>
<style>
header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: rgba(240, 248, 255, 0.326);
    backdrop-filter: blur(20px);
}

.menu-btn-wrap {
    all: unset;
    cursor: pointer;
    display: none;

}

.menu-btn-pic {
    width: 20px;
    height: 20px;
}

.header-wrap {
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: 1000px;
    padding: 0 20px;
    margin: 0 auto;
    height: 80px;
}

a {
    text-decoration: none;
    color: #000;
}

.logo {
    font-size: 20px;
    font-weight: 700;
    color: #000;
}

.router-link-active {
    color: #c2c41a;
}

.nav-links {
    display: flex;
    list-style: none;
    gap: 40px;
}

.menu-active {
    display: flex !important;
}

@media screen and (max-width: 500px) {
    .nav-links {
        flex-direction: column;
        align-items: center;
        justify-content: center;
        width: 100%;
    }

    .nav-wrap {
        display: none;
        position: absolute;
        top: 80px;
        left: 0;
        width: 100%;
        background-color: aliceblue;
        height: calc(100svh - 80px);
    }

    .menu-btn-wrap {
        display: flex;
        align-items: center;
    }
}
</style>
