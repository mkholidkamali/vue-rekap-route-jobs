<template>
    <h1>Available Jobs : </h1>
    <div v-if="jobs.length">
        <div v-for="job in jobs" :key="job.id" class="job">
            <router-link :to="{ name: 'jobDetails', params: { id: job.id } }">
                <h2>{{ job.name }}</h2>
            </router-link>
        </div>
    </div>
    <div v-else>
        <h1>Load jobs data...</h1>
    </div>
</template>

<script>
export default {
    data() {
        return {
            jobs: []
        }
    },
    mounted() {
        fetch('http://localhost:3000/jobs')
            .then(res => res.json())
            .then(data => this.jobs = data)
            .catch(err => console.log(err.message))
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