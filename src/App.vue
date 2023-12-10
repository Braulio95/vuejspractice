<template>
    <navbar
    :pages="pages"
    :active-page="activePage"
    :nav-link-click="(index)=>activePage = index"
    ></navbar>
    <page-viewer
    :page="pages[activePage]"
    ></page-viewer>
</template>


<script>
import PageViewer from './components/PageViewer.vue';
import Navbar from './components/Navbar.vue';
    export default{
        components:{
            Navbar,
            PageViewer
        },
        data(){
            return{
                activePage:0,
                pages: [
                    {
                        link: {text:'Home',url:'index.hmtl'},
                        pageTitle: 'Home Page',
                        content: 'This is the home content'
                    },
                    {
                        link: {text:'About',url:'about.hmtl'},
                        pageTitle: 'About Page',
                        content: 'This is the About content'
                    },
                    {
                        link: {text:'Contact',url:'contact.hmtl'},
                        pageTitle: 'Contact Page',
                        content: 'This is the Contact content'
                    }
                ]
            }
        }
    }
</script>