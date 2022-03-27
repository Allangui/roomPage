<template>
    <main :class="isMenuOpen?'bgMenuOpen':null">
        <div class="container">
            <button>
                <svg @click="isMenuOpen=true" width="20" height="16" xmlns="http://www.w3.org/2000/svg"><path d="M20 12v2H0v-2h20zm0-6v2H0V6h20zm0-6v2H0V0h20z" fill="#FFF" fill-rule="evenodd"/></svg>
            </button>
            <title>room</title>
        </div>
        <Transition mode="out-in">
            <div class="slideMenu" :class="isMenuOpen?'menuTransition':null" v-show="isMenuOpen">
                <button>
                    <svg  width="20" @click="isMenuOpen=false" height="16" xmlns="http://www.w3.org/2000/svg"><path d="M14.364.222l1.414 1.414L9.414 8l6.364 6.364-1.414 1.414L8 9.414l-6.364 6.364-1.414-1.414L6.586 8 .222 1.636 1.636.222 8 6.586 14.364.222z" fill="#000" fill-rule="evenodd" opacity=".201"/></svg>
                </button>
                <nav>
                    <a href="#">home</a>
                    <a href="#">shop</a>
                    <a href="#">about</a>
                    <a href="#">contact</a>
                </nav>
            </div>
        </Transition>
    </main>
</template>

<script>
    export default {
        data() {
            return {
                isMenuOpen: false,
            }
        },
    }
</script>

<style lang="scss" scoped>
.bgMenuOpen{
    position:fixed;
    width: 100%;
    height:100%;
    z-index: 999;
    background-color: rgba(0,0,0,0.7);
    transition: all 1s ease-in-out;
    
}
main{

    .container{
        padding:40px 20px;
        display:flex;
        position:absolute;
        z-index: 998;
        top:0;
        left:0;
        width:100%;
        button{
            background-color: transparent;
            border:none;
            flex-grow: 0;
        }
        title{
            display: inline-block;
            font-size:2rem;
            font-weight: 600;
            color:white;
            letter-spacing: 1px;
            flex-grow: 1;
            text-align: center;
        }
    }
    .v-enter-active,.v-leave-active{
        transition: all 1s ease-in-out;
    }
    .v-enter-from,
    .v-leave-to {
        transform: translateY(-100%);
    }

    .slideMenu{
        position: absolute;
        width:100vw;
        height:auto;
        min-height: 100px;
        z-index: 1000;
        top:0;
        background-color:white ;
        display:flex;
        justify-content: space-between;
        
        button{
            background-color: transparent;
            border:none;
            flex-grow: 0;
            padding:30px;
        }
        nav{
            display: flex;
            column-gap: 5vw;
            flex-wrap: wrap;
            align-items: center;
            padding-right: 20px;
            a{
                text-decoration: none;
                color:black;
                font-size: 1.3rem;
                font-weight: 700;
                padding:20px 0;
            }
        }
    }
}
</style>