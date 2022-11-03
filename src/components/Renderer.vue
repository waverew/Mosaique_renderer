<template>
    <div>
        <div>
            <NavBar>
            
            </NavBar>
        
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
                <Button :text1="butt" :id="sty">

                </Button>
            </div>
        </div>
    
    </div>

</template>
<script>
import json from "./DisplayObjects.json"
import Header from "./Header.vue"
import Image from "./Image.vue"
import NavBar from "./NavBar.vue";
import Title from "./Title.vue";
import Button from "./Button.vue";
import {ref} from "vue";
export default {
    name: "Renderer",
    components:{
        Button,
        Title,
        Image,
        Header,
        NavBar
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
            sty:ref("but")
        };
    },
    methods: {
        changeStyle(mess) {
            this.sty = mess;
        }
    },
    created() {
        
    },
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
#but{
    
    color:white;
    background-color: rgba(21, 24, 184, 0.408);

}
#ass{
    color:black;
    background-color: brown;
}


</style>