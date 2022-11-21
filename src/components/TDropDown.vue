<template>
    <div>
        <label>
            Template
         </label>
        <select>
            <option>
                <button @click="$emit('fun1')">
                    {{text1}}
                </button>
            </option>
            <option>
                <button @click="$emit('fun2')">
                    {{text2}}
                </button>
            </option>
        </select>
    </div>
</template>
<script>
export default{
    name:"TDropDown",
    props:{
        text1: String,
        text2: String
    },
    data(){
        return {
            

        }
    },
    methods:{
        
    }
}

</script>
<style>
#but1{
    
    color:white;
    background-color: rgba(21, 24, 184, 0.408);

}
#but2{
    color:black;
    background-color: brown;
}
</style>