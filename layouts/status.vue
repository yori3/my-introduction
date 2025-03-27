<template>

    <div class="infoBox">
        <slot />
    </div>

</template>

<style lang="scss" scoped>

.infoBox{
    display: grid;
    grid-template-columns: calc((100% - .75em) / 2) calc((100% - .75em) / 2);
    gap: .75em;
    position: relative;
    height: 100%;
    overflow: hidden;
}

</style>