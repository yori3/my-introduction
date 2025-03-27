<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
    mounted() {
        const currentDir: string = (this as any).$route.name;
        let currentTab: HTMLElement | null = null;

        if (currentDir !== 'index') {
            currentTab = document.querySelector(`.tabMenu__item[href*="${currentDir}"]`);
        } else {
            currentTab = document.querySelector('.tabMenu__item[href="/"]');
        }

        if (currentTab) {
            currentTab.classList.add('is-current');
        } else {
            console.error('Current tab element not found.');
        }
    }
})

</script>

<template>
    <nav class="tabMenu">
        <NuxtLink to="/" class="tabMenu__item">profile</NuxtLink>
        <NuxtLink to="/skill/" class="tabMenu__item">skill</NuxtLink>
    </nav>
</template>

<style lang="scss" scoped>
.tabMenu{
    display: grid;
    grid-template-columns: repeat(auto-fill,minmax(6.25em,1fr));
    align-items: flex-end;
    width: 20em;
    margin-left: 1em;
    &__item{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 3em;
        border: 1px solid $mainColor;
        border-radius: 10px 10px 0 0;
        background-color: #fff;
        color: #333;
        &.is-current{
            height: 3.5em;
            background-color: $mainColor;
            color: #fff;
            font-weight: bold;
        }
    }
}
</style>
