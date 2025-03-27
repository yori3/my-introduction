<script lang="ts">
import { defineComponent } from 'vue';

export type DataType = {
  minds: string;
};
export default defineComponent({
    name: "",
    data():DataType {
        return {
            'minds':[
                'すぐに返事をすることで仕事をスムーズに進めることができるのと、相手にも伝わっているという安心感を与えることができると考えているため、レスポンスはなるべく早くするように心がけています。また、早いだけでなく相手にしっかりと伝わる伝え方も意識して伝えています。',
                '制作は一人で進めるということはほぼなく、一緒に進めるメンバーがいるものですので、そのメンバーとの連携を大事にしています。自分の伝えたいことが伝わるように、相手の伝えたいことをしっかりとくみ取って、お互いにやりやすくなるよう心がけています。',
                '更新したときに余白が詰まってしまったりレイアウトが崩れてしまったりしないように、どの要素が増えても、減っても、どこかに移動してもページが崩れず成立する、そんな設計を考えています。'
            ]
        };
    },
    methods:{
        mindDetails: function(index): void{
            const selector = document.querySelectorAll('.mindTitle');
            const exclusion = document.querySelectorAll('.mindTitle.is-current');
            const output = document.getElementById('mindDetail');
            const mindDetailText = this.minds[(index - 1)];
            selector[(index - 1)].classList.add('is-current');
            if(exclusion[0] != null){
                exclusion[0].classList.remove('is-current');
            }
            output.innerHTML = mindDetailText;
        },
        mindDetailsHide: function(): void {
            const exclusion = document.querySelectorAll('.mindTitle.is-current');
            const output = document.getElementById('mindDetail');
            exclusion[0].classList.remove('is-current');
            output.innerHTML = '';
        }
    }
})
</script>
<template>
    <div class="mindBlock">
        
        <div class="flex gap-6">
            <div class="flex-shrink-0">
                <h2 class="text-xl font-bold mb-4">大事にしていること</h2>
                <div class="mb-3">
                    <h2 class="mindTitle font-bold cursor-pointer">素早いレスポンス</h2>
                    <div class="mindDetail">すぐに返事をすることで仕事をスムーズに進めることができるのと、相手にも伝わっているという安心感を与えることができると考えているため、レスポンスはなるべく早くするように心がけています。また、早いだけでなく相手にしっかりと伝わる伝え方も意識して伝えています。</div>
                </div>
                <div class="mb-3">
                    <h2 class="mindTitle font-bold cursor-pointer">メンバーとの連携</h2>
                    <div class="mindDetail">制作は一人で進めるということはほぼなく、一緒に進めるメンバーがいるものですので、そのメンバーとの連携を大事にしています。自分の伝えたいことが伝わるように、相手の伝えたいことをしっかりとくみ取って、お互いにやりやすくなるよう心がけています。</div>
                </div>
                <div>
                    <h2 class="mindTitle font-bold cursor-pointer">運用まで考えた設計</h2>
                    <div class="mindDetail">更新したときに余白が詰まってしまったりレイアウトが崩れてしまったりしないように、どの要素が増えても、減っても、どこかに移動してもページが崩れず成立する、そんな設計を考えています。</div>
                </div>
            </div>
            <!-- <div>
                <div class="mindDetail" id="mindDetail" @click.self="mindDetailsHide()"></div>
            </div> -->
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .mindBlock{
        position: relative;
    }
    div:has(>.mindDetail){
        position: absolute;
        right: 0;
        top: 0;
        width: 80%;
    }
    .mindDetail{
        padding: 1em;
        border-radius: var(--radius-default);
        background-color: #333;
        z-index: 100;
        &:empty{
            display: none;
        }
    }
    .mindTitle{
        display: flex;
        align-content: center;
        &::before{
            display: block;
            margin-right: .25em;
            font-size: 1.25em;
            font-weight: normal;
            font-family: 'Material Symbols Outlined';
            line-height: 1;
            content: "\e887";
        }
        &.is-current{
            pointer-events: none;
        }
    }
</style>