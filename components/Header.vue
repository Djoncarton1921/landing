<template>
    <header class="header">
        <div class="header__content">
            <div class="header__menu">
                <ul class="menu__body">
                    <img class="menu__logo" src="../public/main-logo.svg" />
                    <template class="menu__list" :key="`navItem-${i}`" v-for="(n, i) in nav">
                        <li class="menu__item">
                            <NuxtLink class="menu__link" :to="n.link">
                                {{ n.name }}
                            </NuxtLink>
                        </li>
                    </template>
                    <button class="menu__button"><span>Зареєструватися</span></button>
                </ul>
            </div>
        </div>
    </header>
</template>

<script setup>
const nav = [
    {
        name: "Створення команд",
        link: "/#"
    },
    {
        name: "Організація подій",
        link: "/#"
    },
    {
        name: "Оцінка заходів",
        link: "/#"
    },
    {
        name: "Особистий кабінет",
        link: "/#"
    },
]
</script>

<style lang="scss" scoped>
@import "assets/css/main.scss";

.header {
    height: 68px;
    max-width: 1200px;
    margin: 27px auto;
    box-shadow: 4px 4px 20px rgba(122, 173, 170, 0.2);
    border-radius: 32px;

}

.menu {
    &__body {
        padding: 10px 0;
        align-items: center;
        display: flex;
        justify-content: flex-end;
    }

    &__item {
        margin-left: 30px;
    }

    &__link {
        font-family: 'Inter';
        font-weight: 400;
        font-size: 14px;
        line-height: 20px;
        color: #262541;
        flex: none;
        order: 0;
        flex-grow: 0;
        transition: color 0.3s ease 0s;

        @media(min-width: $md2) {
            &:hover {
                color: red;
            }
        }
    }

    &__button {
        display: flex;
        flex-direction: row;
        align-items: center;
        padding: 8px 16px;
        margin-right: 20px;
        gap: 6px;
        width: 163px;
        height: 40px;
        background: #148783;
        border-radius: 8px;
        flex: none;
        order: 1;
        flex-grow: 0;
        margin-left: 150px;
        transition: background-color 0.4s ease 0s;

        @media(min-width: $md2) {
            &:hover {
                background-color: #1da19d;
            }
        }

        span {
            width: 131px;
            height: 24px;
            font-family: 'Inter';
            font-style: normal;
            font-weight: 600;
            font-size: 15px;
            line-height: 24px;
            text-align: center;
            color: #FFFFFF;
            flex: none;
            order: 1;
            flex-grow: 0;
        }
    }

}
</style>