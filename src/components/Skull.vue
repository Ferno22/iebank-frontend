<template>
    <div>
        <h1>Skull</h1>
        <p>{{ msg }}</p>
        <button type="button" class="btn btn-secondary">
            Skull button
        </button>

    </div>
</template>
 
<script>
import axios from 'axios'
export default
{
    name: 'Skull',
    data()
    {
        return {
            msg: 'Hi! This is the skull component 💀'
        }
    },
    methods:
    {
        getSkull()
        {
            axios.get('${process.env.VUE_APP_ROOT_URL}/skull')
            .then(response => (this.msg = response.data))
            .catch(error => console.log(error))
        }
    },
    created()
    {
        this.getSkull()
    }

    
}
</script>
