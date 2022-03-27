<template>
    <main>
        <MenuMobile v-if="mq.s"/>
        <MenuDesktop v-else/>
        <div :class="mq.m ? 'flexForDesk': null">
            <div class="sec">
                <Transition mode="out-in" v-if="mq.s" >
                    <img v-show="this.subPage==1" src="../../public/mobile-image-hero-1.jpg" alt="image">
                    </Transition>
                    <Transition mode="out-in" >
                    <img v-show="this.subPage==2" src="../../public/mobile-image-hero-2.jpg" alt="image">
                    </Transition>
                    <Transition mode="out-in" >
                    <img v-show="this.subPage==3" src="../../public/mobile-image-hero-3.jpg" alt="image">
                </Transition>
                <Transition mode="out-in" v-if="mq.m" >
                    <img v-show="this.subPage==1" src="../../public/desktop-image-hero-1.jpg" alt="image">
                    </Transition>
                    <Transition mode="out-in" >
                    <img v-show="this.subPage==2" src="../../public/desktop-image-hero-2.jpg" alt="image">
                    </Transition>
                    <Transition mode="out-in" >
                    <img v-show="this.subPage==3" src="../../public/desktop-image-hero-3.jpg" alt="image">
                </Transition>
                <div class="divBtnSlider">
                    <ButtonSlider v-if="mq.s" @changeSubPage="whichSubPage($event)"/>
                </div>
            </div>
            <article>
                <Transition mode="out-in">
                    <div class="forTranslate" v-show="this.subPage == 1">
                        <h1>Discover innovative ways to decorate</h1>
                        <p>
                            We provide unmatched quality, comfort, and style for property owners across the country. 
                            Our experts combine form and function in bringing your vision to life. Create a room in your 
                            own style with our collection and make your property a reflection of you and what you love.
                        </p>
                        <button>shop now <svg width="40" height="12" xmlns="http://www.w3.org/2000/svg"><path d="M34.05 0l5.481 5.527h.008v.008L40 6l-.461.465v.063l-.062-.001L34.049 12l-.662-.668 4.765-4.805H0v-1h38.206l-4.82-4.86L34.05 0z" fill="#000" fill-rule="nonzero"/></svg></button>
                    </div>
                </Transition>
                <Transition mode="out-in">
                    <div class="forTranslate" v-show="this.subPage==2">
                        <h1>We are available all across the globe</h1>
                        <p>
                            With stores all over the world, it's easy for you to find furniture for your home or place of business. 
                            Locally, we’re in most major cities throughout the country. Find the branch nearest you using our 
                            store locator. Any questions? Don't hesitate to contact us today.
                        </p>
                        <button>shop now <svg width="40" height="12" xmlns="http://www.w3.org/2000/svg"><path d="M34.05 0l5.481 5.527h.008v.008L40 6l-.461.465v.063l-.062-.001L34.049 12l-.662-.668 4.765-4.805H0v-1h38.206l-4.82-4.86L34.05 0z" fill="#000" fill-rule="nonzero"/></svg></button>
                    </div>
                </Transition>
                <Transition mode="out-in">
                    <div class="forTranslate" v-show="this.subPage==3">
                        <h1>Manufactured with the best materials</h1>
                        <p>
                            Our modern furniture store provide a high level of quality. Our company has invested in advanced technology 
                            to ensure that every product is made as perfect and as consistent as possible. With three decades of 
                            experience in this industry, we understand what customers want for their home and office.
                        </p>
                        <button>shop now <svg width="40" height="12" xmlns="http://www.w3.org/2000/svg"><path d="M34.05 0l5.481 5.527h.008v.008L40 6l-.461.465v.063l-.062-.001L34.049 12l-.662-.668 4.765-4.805H0v-1h38.206l-4.82-4.86L34.05 0z" fill="#000" fill-rule="nonzero"/></svg></button>
                    </div>    
                </Transition>
                <div class="divBtnSlider">
                    <ButtonSlider v-if="mq.m" @changeSubPage="whichSubPage($event)"/>
                </div>
            </article>
        </div>
    </main>
</template>

<script>
import menuMobile from "./menuMobile.vue"
import menuDesktop from "./menuDesktop.vue"
import buttonSlider from "./buttonSlider.vue"
export default {
    inject:["mq"],
    components: {
        MenuMobile : menuMobile,
        MenuDesktop : menuDesktop,
        ButtonSlider : buttonSlider
    },
    data() {
        return {
            subPage: 1,
        }
    },
    methods: {
        whichSubPage(value) {
            if(value=='left'){
                document.documentElement.style.setProperty('--transiLeft', 'translateX(-100%)')
                document.documentElement.style.setProperty('--transiRight', 'translateX(100%)')
                if(this.subPage==1){
                    this.subPage= 3
                }else{
                this.subPage--
                }
            }else if(value == 'right'){
                document.documentElement.style.setProperty('--transiLeft', 'translateX(100%)')
                document.documentElement.style.setProperty('--transiRight', 'translateX(-100%)')
                if(this.subPage==3){
                    this.subPage=1
                }else{
                this.subPage++
                }
            }
        }
    },
}
</script>

<style lang="scss" scoped>
main{
    .flexForDesk{
        display:flex;
        height: 500px;
        .sec{
            width:60%;
            height:100%;
            overflow: hidden;
        }
        article{
            width:40%;
            height:100%;
            overflow: hidden;
            .forTranslate{
                padding:100px 30px 7vw 70px;
                h1{
                    font-size: 2.5rem;
                    margin-bottom:20px;
                }
                p{
                    line-height: 1.7rem;
                }
                button{
                    margin-top:2vw;
                }
            }
        }
    }
    .v-enter-active,.v-leave-active{
        transition: all .5s ease-in-out;
    }
    .v-enter-from{
        transform: var(--transiLeft);
    }
    .v-leave-to {
        transform: var(--transiRight);
    }
    .v-enter-to{
        
    }
    .v-leave-from{
        
    }
    .sec{
        position: relative;
        height:90vw;
        max-height: 600px;
        img{
            width:100%;
            height:100%;
            top:0;
            left:0;
            position:absolute;
        }
        .divBtnSlider{
            position: absolute;
            bottom:0;
            right: 0;
        }
    }
    article{
        
        position: relative;
        height:400px;
        .forTranslate{
            position: absolute;
            height:auto;
            padding:70px 25px;
        }
        h1{
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 15px;
        }
        p{
            color: hsl(0, 0%, 63%);
            line-height: 1.5rem;
        }
        button{
            font-size: 1.3rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 13px;
            color: hsl(0, 0%, 27%);
            background-color: transparent;
            border:none;
            margin-top:40px;
            padding:10px 0;
            cursor: pointer;
            &:hover{
                opacity: .5;
            }
        }
        .divBtnSlider{
            position: absolute;
            bottom:0;
            left: 0;
        }
    }
}

</style>