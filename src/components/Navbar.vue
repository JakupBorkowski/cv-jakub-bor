<template>
    <nav :class="[`navbar-dark`, `bg-dark`, 'navbar', 'navbar-expand-lg']">
            <div class="container-fluid">
                <a class="navbar-brand" href="#">CV</a>
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li v-for="(page,index) in pages" class="nav-item" :key="index">
                        <router-link :to="`/${page.link.url}`"
                        class="nav-link"
                        active-class="active">
                        {{page.link.text}}
                    </router-link>
                    </li> 
                </ul>
                <form class="d-flex">
                    <button
                    style = "background-color: transparent; margin: 0; padding: 0; border: none;"
                    @click.prevent="changeLanguage()"
                    ><img padding="0" margin="0" width="50" height="25"  :src="require(`@/assets/${flag_source}`)" alt=""></button>
                </form>
            </div>
        </nav>
    </template>
    
    <script>
    export default{
        created(){
            this.getThemeSetting();
        },
        data(){
            return{
                flag_source: "pl_flag.png",
                theme: 'english',
                pages: [{
                    link: {text: "Home", url: ""},
                },
                {
                    link: {text: "About", url: "about"},
                },
                {
                    link: {text: "Contact", url: "contact"},
                },
                {
                    link: {text: "FutureHomePage", url: "homepage"},
                }],
            }
        },
        methods: {
            changeLanguage(){
                let theme = 'english';
                let flag_source = "pl_flag.png"
                let pages = [{
                                    link: {text: "Home", url: ""},
                                },
                                {
                                    link: {text: "About", url: "about"},
                                },
                                {
                                    link: {text: "Contact", url: "contact"},
                                },
                                {
                                    link: {text: "FutureHomePage", url: "homepage"},
                                }];
                if(this.theme == 'english'){
                        theme = 'polish';
                        flag_source = "en_flag.png";
                        pages = [{
                                        link: {text: "Główna", url: ""},
                                    },
                                    {
                                        link: {text: "O mnie", url: "about"},
                                    },
                                    {
                                        link: {text: "Kontakt", url: "contact"},
                                    },
                                    {
                                        link: {text: "Nowa Główna", url: "homepage"},
                                    }];
                }
                this.flag_source = flag_source;
                this.pages = pages;
                this.theme = theme;
                this.storeThemeSetting();
            },
            storeThemeSetting(){
                localStorage.setItem('theme',this.theme);
            },
            getThemeSetting(){
                let theme = localStorage.getItem('theme');
    
                if(theme){
                    this.theme = theme;
                }
            }
        }
    }
    </script>

    <style scoped>
    *{
        margin: 0;
    }
    </style>