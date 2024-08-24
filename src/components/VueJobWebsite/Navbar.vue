<script setup>
    import Logo from '@/assets/VueLogo.png';
    const lists = [
        {id: 1, item : "Home"},
        {id: 2, item: "Job"},
        {id: 3, item: "About Us"},
        {id: 4, item: "Contact Us"}]

</script>

<template>
    <nav class="nav bg-green-600 text-white p-5 ">
        <div class="container flex text-center justify-center mx-auto mx-30">
            <div class="banner flex items-center justify-start">
                <img :src="Logo" width="60" alt="Vue Logo">
                <span class="text-3xl font-bold">Vue Job</span>
            </div>
            <div class="content flex ml-20">
                <ul v-for="list in lists" class="list flex items-center justify-between gap-12">

                    <li v-if="list.id === 1" class="list-item font-semibold px-5 py-2 rounded-md bg-slate-500">
                        {{ list.item }}
                    </li>
                    <li v-else class="list-item px-5 py-2">
                        {{ list.item }}
                    </li>
                </ul>
            </div>
            <div class="flex items-center">
                <button class="add ml-20 mx-5 px-5 py-2 rounded-xl bg-green-800 hover:bg-green-500">Add Job +</button>
                <button class="start bg-slate-900 rounded-md px-5 py-2">Get Started</button>

            </div>
        </div>

    </nav>
</template>

<style scoped>
.add {
    transform: scale(0.9);
    transition: all 0.4s ease-in;
}

.add:hover {
    transform: scale(1.05);
}
.start {
    transform: translateX(0);
    transition: all 0.7s ease;
}
.start:hover{
    transform: translateX(20px);
  }

</style>