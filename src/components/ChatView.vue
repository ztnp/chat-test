<template>
    <el-container>
        <el-aside width="20%">Aside</el-aside>
        <el-container>
            <el-main class="chat-main">
                <el-scrollbar>
                    <!-- <p v-for="item in 50" :key="item" class="scrollbar-demo-item">{{ item }}</p> -->
                    <div class="text-item">
                        <span>
                            {{ ask_test }}
                        </span>
                    </div>

                    <div class="text-item reply-item">
                        <span>
                            {{ reply_test }}
                        </span>
                    </div>

                </el-scrollbar>
            </el-main>
            <el-footer height="12%">
                <!-- <el-form> -->
                    <el-input class="text-input" v-model="reply" ></el-input>
                <!-- </el-form> -->
                <div class="chat-message">ChatGPT Jan 30 Version. Free Research Preview.</div>
            </el-footer>
        </el-container>
    </el-container>
</template>
  

<script>
export default {
    name: "ChatView",
    data() {
        return {
            ask_test: "钢铁侠是什么",
            reply_test: "钢铁侠是一个超级英雄角色，是漫威漫画旗下的著名角色。他的真实身份是富有的工业家Tony Stark，在一次战争中被绑架后，他创造了一个铁制的战斗机甲来保护自己，并成为钢铁侠。作为钢铁侠，他使用先进的科技和武器来打击犯罪和恶势力。",

            ask: "",
            reply: ""

        }
    },

    methods: {
        request_chat_server: () => {
            this.reply = "ask: " + this.ask
        }
    }

}
</script>


<style>
.el-container {
    height: 100%;
}

main.el-main.chat-main {
    /* padding-top: 0;
    padding-left: 0; */
    padding: 0;
}

.el-aside {
    background-color: rgb(32, 33, 35);
}

.text-item {
    float: left;
    padding-top: 22px;
    padding-bottom: 22px;
    padding-left: 11%;
    padding-right: 16%;
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
}


.el-input.text-input {
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
