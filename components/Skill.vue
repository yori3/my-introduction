<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
    mounted() {
        const skillElms = document.querySelectorAll('[data-star]');
        skillElms.forEach(skillElm => {
            const skillVal = skillElm.dataset.star;
            const fragment = document.createDocumentFragment();
            for(let i = 0; i < skillVal; i++){
                const star = document.createElement('span');
                star.classList.add('material-symbols-outlined');
                star.innerText= 'star';
                fragment.appendChild(star);
            }
            skillElm.appendChild(fragment);
        })
    }
})
</script>
<template>
    <div class="skillBlock">
        <h2 class="text-lg font-bold mb-2">Skill（5段階）</h2>
        <table>
            <tbody>
                <tr>
                    <th class="text-left">html</th>
                    <td data-star="5"></td>
                </tr>
                <tr>
                    <th class="text-left">css</th>
                    <td data-star="5"></td>
                </tr>
                <tr>
                    <th class="text-left">scss</th>
                    <td data-star="5"></td>
                </tr>
                <tr>
                    <th class="text-left">Javascript</th>
                    <td data-star="3"></td>
                </tr>
                <tr>
                    <th class="text-left">Vue.js</th>
                    <td data-star="2"></td>
                </tr>
                <tr>
                    <th class="text-left">Nuxt.js(学習中)</th>
                    <td data-star="1"></td>
                </tr>
                <tr>
                    <th class="text-left">astro.js(学習中)</th>
                    <td data-star="1"></td>
                </tr>
                <tr>
                    <th class="text-left">WordPress</th>
                    <td data-star="4"></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<style lang="scss">
.skillBlock{
    table{
    }
    th{
        padding: 0 .5em;
    }
    td{
        padding: 0em .5em;
        color: yellow;
        .material-symbols-outlined{
            font-size: 1.5em;
            font-variation-settings:
            'FILL' 1,
            'wght' 400,
            'GRAD' 0,
            'opsz' 24
        }
    }
}
</style>