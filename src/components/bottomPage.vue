<template>
    <main :class="mq.m? 'mainForDesk':null">
        <img class="imgDark" src="../../public/image-about-dark.jpg" alt="image">
            <article>
                <h2>about our furniture</h2>
                <p>Our multifunctional collection blends design and function to suit your individual taste.
                    Make each room unique, or pick a cohesive theme that best express your interests and what
                    inspires you. Find the furniture pieces you need, from traditional to contemporary styles
                    or anything in between. Product specialists are available to help you create your dream space.
                </p>
            </article>
        <img class="imgLight" src="../../public/image-about-light.jpg" alt="image">
    </main>
</template>

<script>
    export default {
        inject:["mq"],
    }
</script>

<style lang="scss" scoped>
    .mainForDesk{
        display: grid;
        grid-template-columns: 30% 40% 30%;
        grid-template-rows: auto;
        .imgDark{
            grid-column: 1;
            grid-row: 1;
            
        }
        article{
            grid-column: 2;
            grid-row: 1;
            align-self: center;
            padding:0 50px;
            h2{
                font-size:1rem;
            }
        }
        .imgLight{
            grid-column: 3;
            grid-row: 1;
        }

    }
    main{
        border:0;
        margin:0;
        .imgDark,.imgLight{
            width:100%;
        }
        article{
            padding:0 25px;
        h2{
            margin:50px 0 15px 0;
            font-size: 1.3rem;
            font-weight: 700;
            letter-spacing: 5px;
            text-transform: uppercase;
            
        }
        p{
            color: hsl(0, 0%, 63%);
            line-height: 1.5rem;
            margin-bottom: 50px;
        }
        }

    }
</style>