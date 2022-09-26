<template>
    <h1>Available Jobs : </h1>
    <div v-for="job in jobs" :key="job.id" class="job">
        <router-link :to="{ name: 'jobDetails', params: { id: job.id } }">
            <h2>{{ job.name }}</h2>
        </router-link>
    </div>
</template>

<script>
export default {
    data() {
        return {
            jobs: [
                { name: "Graphic Design", id: 1, desc: "lorem" },
                { name: "Web Designer", id: 2, desc: "lorem" },
                { name: "Web Developer", id: 3, desc: "lorem" }
            ]
        }
    }
}
</script>

<style>
.job h2 {
    padding: 20px 0;
    margin: 10px auto;
    background: #eee;
    border-radius: 20px;
    max-width: 600px;
    cursor: pointer;
}
.job h2:hover {
    background: rgba(0, 0, 0, 0.5);
}
.job a {
    text-decoration: none;
    color: black;
}

</style>