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
    </div>
</template>

<style lang="scss" scoped>
.profileBlock{
    display: grid;
    grid-auto-columns: min(20%,400px) 1fr;
    gap: var(--space-default);
    &__image{
        grid-column: 1;
        line-height: 0;
    }
    &__info{
        grid-column: 2;
    }
    &__infoList{
        list-style: none;
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
</style>