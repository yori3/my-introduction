<template>
    <div class="profileBlock">
        <div class="profileBlock__image"><img src="/img/yori3.jpg" alt=""></div>
        <div class="profileBlock__info">
            <ul class="profileBlock__infoList">
                <li><span class="infoList__label">Name</span>yori3</li>
                <li><span class="infoList__label">Place</span>Osaka</li>
                <li><span class="infoList__label">Birth</span>1988.04.01</li>
            </ul>
        </div>
        <div class="accounts grid grid-cols-3">
            <div class="accounts__item ">
                <a href="https://x.com/yori3_otim2" class="block p-2" target="_blank">
                    <img src="/img/x-logo.svg" alt="">
                </a>
            </div>
            <div class="accounts__item">
                <a href="https://github.com/yori3" class="block p-2" target="_blank">
                    <img src="/img/github-mark-white.svg" alt="">
                </a>
            </div>
            <div class="accounts__item">
                <a href="https://profiles.wordpress.org/yori3/" class="block" target="_blank">
                    <img src="/img/wordpress-logo-white.png" alt="">
                </a>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.profileBlock{
    display: grid;
    grid-auto-columns: min(25%,400px) 1fr;
    gap: 1em var(--space-default);
    &__image{
        grid-column: 1;
        line-height: 0;
    }
    &__info{
        grid-column: 2;
    }
    &__infoList{
        list-style: none;
        font-size: 1.25em;
        li{
            &:not(:first-child){
                margin-top: .5em;
            }
        }
    }
}
.infoList{
    &__label{
        &::after{
            display: inline-block;
            margin-right: 0.25em;
            content: ":";
        }
    }
}

.accounts{
}
</style>