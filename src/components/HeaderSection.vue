<script setup>
import { headerNav } from '@/constants'
</script>
<template>
    <header id="header" role="banner">
        <div class="header__inner">
            <h1 class="header__logo">
                <a href="#">portfolio <em>vue.js</em></a>
            </h1>
            <nav
                class="header__nav"
                :class="{ show: isNavVisible }"
                role="navigation"
                aria-label="메인 메뉴"
            >
                <ul>
                    <li v-for="(nav, key) in headerNav" :key="key">
                        <a :href="nav.url" @click="scrollLink($event)">{{ nav.title }}</a>
                    </li>
                </ul>
            </nav>
            <div
                class="header__nav__mobile"
                id="headerToggle"
                aria-controls="primary-menu"
                aria-expanded="false"
                role="button"
                tabindex="0"
                @click="toggleMobileMenu"
            >
                <span></span>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            isNavVisible: false
        }
    },
    methods: {
        toggleMobileMenu() {
            this.isNavVisible = !this.isNavVisible
        },
        scrollLink(event) {
            event.preventDefault()

            const targetId = event.target.getAttribute('href')
            const targetElement = document.querySelector(targetId)

            if (targetElement) {
                targetElement.scrollIntoView({ behavior: 'smooth' })
            }
        }
    }
}
</script>

<style lang="scss">
@import '@/assets/scss/mixin';

#header {
    @include position-fixed;
    z-index: 10000;

    .header__inner {
        @include flex-between;
        background-color: #2e43aede;
        backdrop-filter: blur(15px);
        padding: 1rem;

        .header__logo {
            font-size: 1.5rem;
            text-align: center;
            text-transform: uppercase;
            line-height: 1;
            color: var(--white);

            em {
                font-size: 10px;
                display: block;
                color: var(--white);
                font-weight: 400;
            }
        }
        .header__nav {
            color: var(--white);

            @media (max-width: 800px) {
                display: none;

                &.show {
                    display: block;

                    ul {
                        display: block;
                        position: absolute;
                        right: 0;
                        top: 68px;
                        background-color: #2e43aede;
                        backdrop-filter: blur(15px);
                        z-index: 10000;
                        min-width: 150px;
                        padding: 20px 0;

                        li {
                            display: block;
                            text-align: center;

                            a {
                                display: inline-block;
                                padding: 10px;
                            }
                        }
                    }
                }

                &.show + .header__nav__mobile span::before {
                    top: 8px;
                }
                &.show + .header__nav__mobile span::after {
                    bottom: 8px;
                }
            }

            li {
                display: inline;

                a {
                    text-transform: uppercase;
                    font-size: 1rem;
                    padding: 14px;
                    position: relative;
                    font-weight: 400;

                    &::before {
                        content: '';
                        height: 1px;
                        width: calc(100% - 28px);
                        background-color: #ee7894;
                        position: absolute;
                        left: 14px;
                        bottom: 10px;
                        transform: scaleX(0);
                        transition: all 0.3s;
                    }
                    &:hover::before {
                        transform: scaleX(1);
                    }
                }
            }
        }
        .header__nav__mobile {
            display: none;
            width: 40px;
            height: 40px;
            cursor: pointer;

            @media (max-width: 800px) {
                display: block;
            }

            span {
                display: block;
                width: 40px;
                height: 2px;
                background-color: var(--white);
                margin-top: 19px;
                position: relative;

                &::before {
                    content: '';
                    width: 40px;
                    height: 2px;
                    background-color: var(--white);
                    position: absolute;
                    right: 0;
                    top: 6px;
                    transition: width 0.3s;
                }
                &::after {
                    content: '';
                    width: 40px;
                    height: 2px;
                    background-color: var(--white);
                    position: absolute;
                    right: 0;
                    bottom: 6px;
                    transition: width 0.3s;
                }
            }
        }
    }
}
</style>
