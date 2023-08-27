<template>

    <img :src="source + '/neck/' + options[0] + '.png' " class="neck" >
    <img :src="source + '/eyes/' + options[1] + '.png' " class="eyes">
    <img :src="source + '/nose' + '.png' " class="nose">
    <img :src="source + '/mouth/' + options[2] + '.png' " class="mouth">
    

</template>

<script>
import { ref } from 'vue';

export default {

    setup(props){

        const source = "/src/assets";
        return {
            source,
            options: props.options
        }
    },
    props: {
        options: Array
    }
}

</script>

<style scoped>

.bordered {
    border: 1px solid white;
}

img {
    height: 200px;
    width: 200px;
}

.neck {
    position: fixed;
    z-index: 1;
}

.eyes {
    position: fixed;
    z-index: 2;

    transform: translate(0, 0);
}

.nose {
    position: fixed;
    z-index: 2;

    transform: translate(0, 0);
}

.mouth {
    position: fixed;
    z-index: 3;

    transform: translate(0, 0);
}

</style>