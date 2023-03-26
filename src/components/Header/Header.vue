<template>
    <header class="header">
        <div class="header__content">
            <img  class="header__logo" src="@/assets/logo.png" alt="logo"/>
            <nav class="header__nav">
                <a @click="onClickMenuItem('home')" class="header__nav_link">Home</a>
                <a class="header__nav_link">About</a>
                <a class="header__nav_link">Platform</a>
                <a class="header__nav_link">MVP</a>
                <a class="header__nav_link">Coins</a>
                <a class="header__nav_link">Roadmap</a>
                <a class="header__nav_link">Faqs</a>
                <a class="header__nav_link">Contacts</a>
            </nav>
            <Button v-bind:variant="non-bg"  v-bind:name="Dashboard"/>
        </div>
    </header>
</template>

<script>
import Button from '@/UIKit/Button/Button.vue';
    export default {
    name: 'Header',
    components: {
        Button,
    },
    methods: {
        onClickMenuItem(type) {

        console.log(type);
         console.log("click");
      }        
    }
}

    
</script>

<style lang="scss" scoped>

.header {  
    display: flex;
    width: 100%;
    max-height: 100px;
    position: fixed !important;
    background-color: transparent;

    &__logo {
        height: 60px;
    }

    &__content {
        display: flex;
        height: 100%;
        margin: 0 auto;

    }

    &__nav {
        display: flex;
        align-items: center;
        gap: 15px;

        &_link {
            font-family: 'Roboto', sans-serif;
            color: white;
            font-size: 15px;
            font-weight: 400px;
            cursor: pointer;
            &:hover {
                color: #f42f54;
            }
        }
    }
}

</style>