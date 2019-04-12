<template>
    <div class="hello">
        <h1>{{ msg }}</h1>
        <span>Multiline message is:</span>
        <p style="white-space: pre-line;">{{ message }}</p>
        <!--<ul>-->
            <!--<li v-for="item in items">-->
                <!--{{ item }}-->
            <!--</li>-->
        <!--</ul>-->
        <br>
        <textarea v-model="message" placeholder="add multiple lines"></textarea>>
    </div>
</template>

<script>
    export default {
        // template: '#task-template',
        // props: ['list'],
        // data: function () {
        //     return {
        //         mutableList: JSON.parse(this.list)
        // }
        // },
        name: 'HelloWorld',
        props: {
            msg: String,
            message: String,
            items: []
        },

        mounted() {
            this.init();
        },

        async init() {
            this.items.push(this.message);
            setInterval(async () => {
                this.client = await this.items.push(this.message);
            }, 60000)
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
