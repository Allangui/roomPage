<template>
    <main>
        <title>room</title>
        <nav>
            <a href="#">home</a>
            <a href="#">shop</a>
            <a href="#">about</a>
            <a href="#">contact</a>
        </nav>
    </main>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
main{
    padding:40px 0;
    display:flex;
    position:absolute;
    color:white;
    z-index: 998;
    top:0;
    left:0;
    title{
        display: inline-block;
        padding:0 60px;
        font-size:3rem;
        font-weight: 400;
        letter-spacing: 1px;
        flex-grow: 1;
        text-align: center;
        align-self: center;
    }
    nav{
        display: flex;
        column-gap: 3vw;
        flex-wrap: wrap;
        align-items: center;
        padding-right: 20px;
        a{
            text-decoration: none;
            color:white;
            font-size: 1.3rem;
            font-weight: 400;
            padding:20px 0;
            position: relative;
            &::after{
                    content:'';
                
            }
            &:hover{
                &::after{
                    content:'';
                    position: absolute;
                    bottom:12px;
                    left:25%;
                    height:4px;
                    width:50%;
                    background-color: white ;
                    opacity:1;
                    transition: all 1s ;
                }
            }
        }
    }

}
</style>