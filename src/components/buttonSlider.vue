<template>
    <main>
        <button :class="mq.s ? 'btnMobile' : 'btnDesktop'" @click="$emit('changeSubPage','left')">
            <svg width="14" height="24" xmlns="http://www.w3.org/2000/svg"><path d="M13 0L1 12l12 12" stroke="#FFF" fill="none" fill-rule="evenodd"/></svg>
        </button>
        <button :class="mq.s ? 'btnMobile' : 'btnDesktop'" @click="$emit('changeSubPage','right')">
            <svg width="14" height="24" xmlns="http://www.w3.org/2000/svg"><path d="M1 0l12 12L1 24" stroke="#FFF" fill="none" fill-rule="evenodd"/></svg>
        </button>
    </main>
</template>

<script>
    export default {
        inject:["mq"],
        emits:['changeSubPage']
    }
</script>

<style lang="scss" scoped>
main{
    display: flex;
    background-color: black;
    .btnMobile,.btnDesktop{
        background-color: black;
        border:none;
        padding:0;
        margin: 0;
        cursor: pointer;
        &:hover{
            background-color:rgba(182, 181, 181, 0.3);
        }
    }
    
    .btnMobile{
        width:17vw;
        max-width: 120px;
        height:15vw;
        max-height:107px ;
    }
    .btnDesktop{
        width:7vw;
        max-width: 85px;
        height:6vw;
        max-height:75px
    }
}
</style>