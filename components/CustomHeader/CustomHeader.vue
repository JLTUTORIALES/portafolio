<template>
    <header>
        <div>
            <h1>Jose Luis Ortiz</h1>
            <h2>Full-Stack Web Developer</h2>
            <p>Apasionado desarrollador web enfocado en crear experiencias digitales excepcionales, comprometido con la excelencia y la innovación en cada línea de código.</p>
            <a id="cv" href="resume.pdf" target="_blank">Descargar CV</a>
            <section>
                <a target="_blank" v-for="contact in contacts"  :href="contact.href" :title="contact.title"><i :class="contact.class"></i></a>
            </section>
        </div>
    </header>
</template>
<script setup>
    import { contacts } from '~/state';
</script>

<style scoped>
    header{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    #cv{
        text-decoration: none;
        cursor: pointer;
        background-color: #222;
        display: inline-block;
        width: 20%;
        padding: 10px;
        text-align: center;
        border-radius: 25px;
        margin: 10px 0px;
        transition: color .2s, transform .2s;
    }
    #cv:hover{
        transform: scale(1.1);
        color: #e66;
    }
    div{
        display: flex;
        flex-direction: column;
        justify-content: center;
        position: fixed;
        width: 45vw;
        height: 100vh;
        top: 0  ;
        padding-left: 5vw;
    }
    h1{
        font-size: 40pt;
        color: #e66;
        font-weight: bold;
        margin-bottom: 15px;
    }
    h2{
        font-weight: lighter;
        font-size: 18pt;
        color: #ddd;
    }
    p{
        margin-top: 15px;
        width: 70%;
        font-size: 12pt;
        text-align: justify;
        color: #999;
        margin-bottom: 25px;
    }
    ul{
        list-style-type: none;
        padding-left: 25px;
        height: auto;
    }
    ul li{
        padding: 12px 0px;
        color: #999;
        cursor: pointer;
        transition: color .2s, transform .2s;
    }

    ul li:hover{
        color: #ddd;
    }

    ul li::before{
        content: '• ';
    }

    ul #active{
        color: #ddd;
        transform: scale(1.1);
    }

    section{
        display: inline-flex;
        flex-direction: row;
        justify-content: space-between;
        width: 40%;
        margin-top: 50px;
        margin-left: 10px;
        font-size: 20pt;
    }

    section a{
        cursor: pointer;
        color: #e66;
        transition: transform .2s;
    }

    section a:hover{
        transform: scale(1.4);
    }

    @media screen and (max-width: 1000px) {
        div {
            position: static;
            width: 90%;
        }
    }
    @media screen and (max-width: 500px) {
        #cv{
            width: 90%;
        }
        p{
            width: 90%;
        }
        section{
            width: 60%;
            align-self: center;
            margin: 15px 0px;
            padding: 0;
        }
    }
</style>