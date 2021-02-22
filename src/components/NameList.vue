<template>
    <div>
        <h3 v-for="name in names" :key="name.firstName"> 
            <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
        </h3>
    </div>
</template>

<script>
    export default {
        name: 'NameList',
        data(){
            return{
                names: [
                    {
                        firstName: 'Maxinne',
                        lastName: 'Mullerman'
                    },
                    {
                        firstName: 'Toni',
                        lastName: 'Lerman'
                    },
                    {
                        firstName: 'Rosi',
                        lastName: 'Nord'
                    },
                ],
            }
        }
        
    }
</script>

<style scoped>
 h3{
     color: red;
 }
</style>