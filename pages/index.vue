<template>
    <div>
        <section id="about">
            <h1 class="section-title">Acerca de</h1>
            <p>{{ description }}</p>
        </section>
        <section id="projects">
            <h1 class="section-title">Proyectos</h1>
            <a class="card" target="_blank" v-for="project in projects" :href="project.target">
                <span class="date">{{ project.date }}</span>
                <div>
                    <span class="title">{{ project.title }}</span>
                    <p>{{ project.summary }}</p>
                    <ul>
                        <li v-for="skill in project.skills">{{ skill }}</li>
                    </ul>
                </div>
            </a>
        </section>
        <section id="experience">
            <h1 class="section-title">Experiencia</h1>
            <a class="card" target="_blank" v-for="exp in experience" :href="exp.target">
                <span class="date">{{ exp.date }}</span>
                <div>
                    <span class="title">{{ exp.title }}</span>
                    <p>{{ exp.summary }}</p>
                    <ul>
                        <li v-for="skill in exp.skills">{{ skill }}</li>
                    </ul>
                </div>
            </a>
        </section>
        <section id="skils">
            <h1 class="section-title">Habilidades</h1>
            <div class="skills">
                <img v-for="skill in skills" :src="skill.src" :title="skill.title" :alt="skill.alt"/>
            </div>
        </section>
    </div>
</template>
<script setup>
    import { skills, experience, projects, description } from '~/state';


    const useImage = (asset) => {
        return import.meta.glob('~/assets/svg/*', {
            eager: true
        })[asset].default
    }
</script>

<style scoped>
    div{
        padding: 25px 0px;
    }
    section{
        padding: 25px;
    }
    #about p{
        width: 90%;
    }
    .section-title{
        color: #e66;
        font-size: 22pt;
        margin-bottom: 25px;
    }
    section p{
        text-align: justify;
        padding-right: 25px;
    }

    .skills{
        display: flex;
        flex-wrap: wrap;
    }
    .skills img{
        width: 80px;
        margin: 15px;
        cursor: pointer;
        transition: transform .2s;
    }
    .skills img:hover{
        transform: scale(1.2);
    }

    .card{
        display: flex;
        text-decoration: none;
        justify-content: space-between;
        align-items: flex-start;
        border-radius: 25px;
        transition: border-color .2s, background-color .2s;
        cursor: pointer;
        padding: 15px;
        width: 80%;
    }

    .card div{
        display: flex;
        flex-direction: column;
        align-content: flex-start;
        padding: 0;
        flex: 2;
    }

    .card div p{
        margin-top: 15px;
        text-align: justify;
    }

    .card .date{
        font-size: 10pt;
        flex: 1;
    }
    .card:hover{
        background-color: #222;
    }

    .card .title{
        color: #ddd;
        font-size: 14pt;
        display: block;
    }
    .card ul{
        display: flex;
        margin-top: 25px;
        list-style-type: none;
        justify-content: flex-start;
        flex-wrap: wrap;
    }
    .card ul li{
        background-color: #666;
        color: #ddd;
        padding: 5px 15px;
        min-width: 10%;
        text-align: center;
        border-radius: 15px;
        transition: border-color .2s, color .2s;
        font-size: 8pt;
        margin: 5px;
        margin-left: 0;
    }
    .card:hover ul li{
        color: #e66;
    }

    @media screen and (max-width: 500px) {
        .card{
            width: 90%;
        }

        #about p{
            width: 100%;
        }
    }
</style>