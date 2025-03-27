<script setup>
import { ref, onMounted } from 'vue'; 
// WordPressのAPIエンドポイント 
const apiEndpoint = 'https://yori3.com/wp-json/wp/v2/posts?per_page=3'; 
// 投稿データを格納するリアクティブ変数 
const posts = ref([]); 
const fetchPosts = async () => { 
    try { 
        const response = await fetch(apiEndpoint); 
        if (response.ok) { 
            posts.value = await response.json(); 
            for(let i=0; i < posts.value.length; i++){ 
                const date = posts.value[i].date; 
                const newDate = date.substr(0,date.indexOf('T')); 
                const changeDate = newDate.replaceAll('-','.'); 
                posts.value[i]['showDate'] = changeDate; 
            } 
        } else { 
            console.error('Failed to fetch posts:', response.status); 
        } 
    } 
    catch (error) { 
        console.error('Error fetching posts:', error); 
    } 
};

// コンポーネントがマウントされたときに投稿を取得
onMounted(fetchPosts);
</script>

<template>
    <div class="blogBlock">
        <h2 class="text-xl font-bold mb-4">Blog</h2>

        <ul class="postArchive">
            <li v-for="post in posts" :key="post.id">
                <a v-bind:href="post.link" class="postBlock" target="_blank">
                    <h2 class="postBlock__title font-bold">{{ post.title.rendered }}</h2>
                    <div class="postBlock__date mt-2">{{post.showDate}}</div>
                </a>
            </li>
        </ul>
    </div>
</template>

<style lang="scss" scoped>
    .postArchive{
        display: flex;
        flex-direction: column;
        gap: 1.5em;
    }
    .postBlock{
        display: block;
        position: relative;
        // height: 100%;
        // padding: var(--space-default);
        // border-radius: var(--radius-default);
        // border: 2px solid currentColor;
        // background-color: $mainColor;
        // transition: .5s;
        // overflow: hidden;
        // z-index: 1;
        // @media(hover){
        //     &:hover{
        //         color: #333;
        //         background-color: #fff;
        //     }
        // }
        &__title{
            font-size: 1.1em;
            text-decoration: underline;
        }
        &__date{
            font-size: .9em;
        }
    }
</style>