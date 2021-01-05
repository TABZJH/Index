<template>
    <div class="index">
        <input type="text" v-model="ipt" v-on:input="inpChange">
        <h3>{{replay}}</h3>
    </div>
</template>

<script>
    export default {
        name: 'Index',
        data() {
            return {
                ipt: '',
                replay: ''
            }
        },
        methods: {
            inpChange(event) {
                this.replay = this.reply(event.target.value);
            },
            reply(str) {
                if (!str) {
                    return "?";
                }
                let rep = str.replace("吗", "");
                rep = rep.replace("?", "!");
                rep = rep.replace("？", "!");
                return rep;
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h3 {
        margin: 40px 0 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>
