<template>
    <el-container>
        <el-aside width="20%">Aside</el-aside>
        <el-container>
            <el-main class="chat-main">
                <el-scrollbar ref="myScrollbar">
                    <div v-for="item in dialogue" :key="item">

                        <div class="text-item">
                            <span>
                                {{ item.ask_text }}
                            </span>
                        </div>

                        <div class="text-item reply-item">
                            <span>
                                {{ item.reply_text }}
                            </span>

                        </div>
                    </div>

                </el-scrollbar>
            </el-main>
            <el-footer height="12%">
                <el-input class="chat-input" v-model="ask" @keyup.enter="chatServer"></el-input>
                <div class="chat-message">ChatGPT Jan 30 Version. Free Research Preview.</div>
            </el-footer>
        </el-container>
    </el-container>
</template>


<script setup>

import { ref } from 'vue'
import { ElScrollbar } from 'element-plus'

const ask = ref("")
const myScrollbar = ref(null)

const dialogue = ref([
    {
        ask_text: "钢铁侠是什么",
        reply_text: "钢铁侠是一个超级英雄角色，是漫威漫画旗下的著名角色。他的真实身份是富有的工业家Tony Stark，在一次战争中被绑架后，他创造了一个铁制的战斗机甲来保护自己，并成为钢铁侠。作为钢铁侠，他使用先进的科技和武器来打击犯罪和恶势力。",
    },
])

function chatServer() {
    dialogue.value.push({ ask_text: ask.value, reply_text: "ask:" + ask.value })
    ask.value = ""

    // console.log(myScrollbar.value)
    console.log(myScrollbar.value.scrollHeight)
    // myScrollbar.value.scrollTo(0, 3500)
    myScrollbar.value.setScrollTop = myScrollbar.value.scrollHeight

}



</script>
  
<!-- 
<script>
export default {
    name: "ChatView",
    data() {
        return {
            dialogue: [
                {
                    ask_text: "钢铁侠是什么",
                    reply_text: "钢铁侠是一个超级英雄角色，是漫威漫画旗下的著名角色。他的真实身份是富有的工业家Tony Stark，在一次战争中被绑架后，他创造了一个铁制的战斗机甲来保护自己，并成为钢铁侠。作为钢铁侠，他使用先进的科技和武器来打击犯罪和恶势力。",
                },
            ],

            ask: "",
        }
    },

    methods: {
        chatServer() {
            console.log("fuck:", this.ask)
            this.dialogue.push({ask_text: this.ask, reply_text: "ask:" + this.ask})
            this.ask = ""
            // this.$refs.leftScrollbar.scrollTop = this.$refs.leftScrollbar.scrollHeight;
            console.log(this.$refs)
            console.log(this.$refs.leftScrollbar)
            this.$refs.leftScrollbar.scrollTo(0, 3500)
        },
    }

}
</script> -->


<style>
.el-container {
    height: 100%;
}

main.el-main.chat-main {
    padding: 0;
}

.el-aside {
    background-color: rgb(32, 33, 35);
}

.text-item {
    width: 100%;
    padding-top: 20px;
    padding-bottom: 20px;
}


.reply-item {
    background-color: rgb(247, 247, 247);
}


span {
    word-break: normal;
    width: auto;
    display: block;
    white-space: pre-wrap;
    word-wrap: break-word;
    overflow: hidden;
    padding-left: 11%;
    padding-right: 11%;
}

.el-input.chat-input {
    width: 80%;
    height: 60%;
    bottom: 10px;
}

.chat-message {
    font-size: .75rem;
    line-height: 1rem;
    color: rgb(146, 146, 147);
}
</style>
