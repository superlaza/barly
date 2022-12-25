<script>
import Bar from "./Bar.vue";

export default {
    name: 'BarList',
    components: {
        Bar
    },
    data() {
        return {
            bars: []
        }
    },
    mounted() {
        fetch('/orlando_bar_data.json')
        .then(response => response.json()) // Parse the response as JSON
        .then(data => {
            // Update the items data property with the response data
            console.log(data)

            var date = new Date;
            var day = date.toLocaleDateString('en-US', { weekday: 'long' }).toLocaleLowerCase()
            var hour = date.getHours() + parseInt(Math.round(date.getMinutes()/60.0));

            for(var bar of data){
                if(Object.keys(bar.popularity).length !== 0){
                    var ix = bar.popularity[day]['hour'].indexOf(hour)
                    var current_density = bar.popularity[day]['density'][ix]
                    bar.current_density = Math.round(10000*current_density)
                }
            }

            data = data.filter(bar => bar.current_density !== undefined)

            data.sort((a, b) => (a.current_density > b.current_density) ? -1 : 1)
            this.bars = data

        })
        .catch(error => {
            // Handle any errors that occurred during the request
            console.error(error);
        });
    }
}
</script>

<template>
    <div id="bar-list">
        <div ref="bars" v-for="bar in bars">
            <!-- <Bar :name="bar.name" /> -->
            <Bar :bar="bar" />
        </div>
    </div>
    <!-- <Bar :bar="bar" /> -->
</template>

<style scoped>
#bar-list {
    width: 100%;
}
</style>