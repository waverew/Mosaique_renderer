<template>
    <div>
        <label>
            Template
         </label>
        <select>
            <option >
                {{text1}}
            </option>
            <option >
                {{text2}}
            </option>
        </select>
    </div>
</template>
<script>
export default{
    name:"TDropDown",
    props:['text1', "text2"],
    data(){
        return {

        }
    },
    methods:{

    }
}

</script>
<style>

</style>