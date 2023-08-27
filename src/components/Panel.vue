<template>

    <button v-for="choice in choices" @click="toggleChoice(choice)">{{ choice }}</button>
    
    <div v-if="current_choice == 1">
        <button v-for="option in neck_options" @click="setOption(option)">{{ option }}</button>
    </div>
    <div v-if="current_choice == 2">
        <button v-for="option in eyes_options" @click="setOption(option)">{{ option }}</button>
    </div>
    <div v-if="current_choice == 3">
        <button v-for="option in mouth_options" @click="setOption(option)">{{ option }}</button>
    </div>


</template>

<script>

import { ref } from 'vue';

export default {

    setup(props, { emit }){
        const choices = [
            'neck',
            'eyes',
            'mouth'
        ];

        const current_choice = ref(1);

        function toggleChoice(choice){
            switch(choice){
                case 'neck': current_choice.value = 1; break;
                case 'eyes': current_choice.value = 2; break;
                case 'mouth': current_choice.value = 3; break;
            }
        }

        const neck_options = ref([
            'default',
            'thick',
            'bend-backward',
            'bend-forward'
        ]);
        const eyes_options = ref([
            'default',
            'angry',
            'naughty',
            'panda',
            'smart',
            'star'
        ]);
        const mouth_options = ref([
            'default',
            'astonished',
            'eating',
            'laugh',
            'tongue'
        ]);

        function setOption(option){
            emit('optionSet', current_choice.value, option);
        }

        return {
            choices,
            current_choice,
            toggleChoice,
            neck_options,
            eyes_options,
            mouth_options,
            setOption
        }
    }
}

</script>

<style>

</style>