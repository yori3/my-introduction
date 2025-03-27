<script setup>
    definePageMeta({ layout: 'status' })
</script>

<template>

    <div class="columnBlock-l">
        <div class="infoBox__inner">
            <PersonalData />
            <div class="mt-4">
                <Profile />
            </div>
        </div>
    </div>
    <div class="columnBlock-r">
        <div class="infoBox__inner">
            <div class="statusBox">
                <Tools />
            </div>
        </div>
        <div class="infoBox__inner">
            <div class="statusBox">
                <Skill />
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.columnBlock-r{
    display: flex;
    flex-direction: column;
    gap: .75em;
    .infoBox__inner{
        flex-basis: calc((100% - .75em) / 2);
        flex-grow: 1;
    }
}
</style>