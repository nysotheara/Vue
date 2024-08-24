<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">My Vue</a>
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li v-for="link in links" class="nav-item">
                    <a class="nav-link" aria-current="page" v-bind:href=link.url>{{ link.text }}</a>
                </li>
            </ul>
        </div>
    </nav>
    <div id="content" class="container">
        <h1>{{ pageTitle }}</h1>
        <p>{{ content }}</p>
    </div>
</template>

<script>
export default {
    data() {
        return {
            links: [
                { text: "Home", url : 'home.html' }, 
                { text : "About", url : 'about.html' }, 
                { text : "Contact", url : 'contact.html' }
            ],
            pageTitle: "Hello Vue",
            content: "Welcome to the wonderful world of Vue JS"
        };
    }
}
</script>