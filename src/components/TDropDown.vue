<template>
    <div>
        <label>
            Template
         </label>
        <select>
            <option>
                <button @click="clicked1">
                    {{text1}}
                </button>
            </option>
            <option>
                <button @click="clicked2">
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
        text2: String,
        fun1: Function,
        fun2: Function
    },
    data(){
        return {
            

        }
    },
    methods:{
        clicked1(){
            this.$emit('fun1');
        },
        clicked2(){
            this.$emit('fun2');
        }
        
    }
}

</script>
<style>

</style>