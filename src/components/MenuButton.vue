<template>
    
    <button  @mouseover="changeBackground('/img/animals.8a99d733.jpg')" class="psychedelic-button  
     text-white text-xl h-24 bg-opacity-40 font-bold py-2 px-4 rounded w-21">
        Animals (1971)
    </button>

</template>
<script >
export default {
    name: 'MenuButton',
    data() {
        return {
            
        }
    },
    methods: {
        
    },
    props: {
    changeBackground: Function
   },
    computed: {
        
    },
    watch: {
        
    },
    mounted() {
        
    }
}
</script>
<style>
.psychedelic-button {
    background-image: url('~@/assets/animals.jpg'); /* Asegúrate de reemplazar la ruta con la ruta real de tu imagen */
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
    border: none;
    cursor: pointer;
    transition: transform 0.2s;
}

.psychedelic-button:hover {
    transform: scale(1.05);
}
</style>