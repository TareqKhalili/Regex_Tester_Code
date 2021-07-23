<template>
    <div class="savedExpressions">


        <table id="savedExp">


            <tr>
                <th>Expression</th>
                <th>Flags</th>
            </tr>


            <tr v-for="(exp, index) in savedExps" :key="exp.id">
                <td> {{ exp }} </td>
                <td> {{ savedFlags[index] }} </td>
            </tr>


        </table>


    </div>
</template>

<script>
export default {
    props: ['savedExps', 'savedFlags'],


    mounted() {
        for ( let i = 0; i < localStorage.length; i++) {
            if (localStorage.key(i) === 'loglevel:webpack-dev-server') {
                continue;
            }
            this.savedExps.push(localStorage.key(i));
            this.savedFlags.push(localStorage[localStorage.key(i)]);
        }
    },


}
</script>

<style>

</style>