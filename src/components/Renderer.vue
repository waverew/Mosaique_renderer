<template>
    <div>
        <div class="nav">
        <TDropDown :text1="dropDownSel1" :text2="dropDownSel2"></TDropDown>
        <TDropDown text1="Style" text2="Style but new" @fun1="changeStyle('but1')" @fun2="changeStyle('but2')" ></TDropDown>
        </div>
            <div>
                <div class="titleBorder">
                <Title :title1="title" class="cont">

                </Title>
                </div>
                <div class="cont">
                    <Image>

                    </Image>
                    <Header :text1="messAge1" :text2="messAge2">

                    </Header>
                </div>
            </div>
            <div class="butcont">
                <Button :text1="butt" :id="sty" @click="changeStyle('but2')">

                </Button>
            </div>
        
    
    </div>

</template>
<script>
import json from "./DisplayObjects.json"
import Header from "./Header.vue"
import Image from "./Image.vue"
//import NavBar from "./NavBar.vue";
import Title from "./Title.vue";
import Button from "./Button.vue";
import TDropDown from "./TDropDown.vue";
import {ref} from "vue";
export default {
    name: "Renderer",
    components:{
        Button,
        Title,
        Image,
        Header,
        TDropDown
},
    data() {
        const byJson = JSON.stringify(json);
        const myJson = JSON.parse(byJson);
        
        return {
            byJson:JSON.stringify(json),
            myJson:JSON.parse(byJson),
            messAge1:myJson[6].menu.options[1].submenu2.text,
            messAge2:myJson[6].menu.options[0].submenu1.text,
            title:myJson[0].title.text,
            butt:myJson[5].button.text,
            dropDownSel1:myJson[10].dropDownSelect.options[0].option.text,
            dropDownSel2:myJson[10].dropDownSelect.options[1].option.text,
            sty:ref("but1")
        };
    },
    methods: {
        changeStyle(mess) {
            this.sty = mess;
        }
    }
}

</script>
<style>
.titleBorder{
    border-bottom: dotted;
}
.cont{ 
    padding: 3%;
    
}
.butcont{
    display: flex;
    margin: 2%;
    height: 3rem;
    justify-content: right;
}
#but1{
    
    color:white;
    background-color: rgba(21, 24, 184, 0.408);

}
#but2{
    color:black;
    background-color: brown;
}
.nav{
    background-color: rgba(104, 51, 106, 0.476);
    display: flex;
    justify-content: space-between;
    border-style:dotted;
}


</style>