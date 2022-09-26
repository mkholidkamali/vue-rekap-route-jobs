<template>
    <h1>Job Details Page</h1>
    <P>The job id is : {{ id }}</P>
</template>

<script>
export default {
    props: ['id']
    // data() {
    //     return {
    //         id: this.$route.params.id
    //     }
    // }
}
</script>

<style>

</style>