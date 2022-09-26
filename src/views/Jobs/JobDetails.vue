<template>
    <div v-if="job">
        <h1>{{ job.name }}</h1>
        <p>The job id is : {{ job.id }}</p>
        <p>Description : {{ job.desc }}</p>
    </div>
    <div v-else>
        <h1>Loading Job Details...</h1>
    </div>
</template>

<script>
export default {
    props: ['id'],
    data() {
        return {
            // id: this.$route.params.id
            job: null
        }
    },
    mounted() {
        fetch('http://localhost:3000/jobs/' + this.id)
            .then(res => res.json())
            .then(data => this.job = data)
            .catch(err => console.log(err))
    }
}
</script>

<style>

</style>