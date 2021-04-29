<template>
    <div>
        <v-row justify="center">
        <v-col cols="4" class="mx-auto">
            <v-text-field outlined :color="showError ? 'red' : 'blue'" v-model="inputText" @keyup.enter="addComment()" label="comment"></v-text-field>
        </v-col>
        </v-row>

        <v-row justify="center">
        <v-col class="mx-auto" cols="4">
            <v-card
            v-for="(comment, i) in localcomments"
            :key="i"
            elevation="2"
            outlined
            class="my-2"
            >
            <v-card-text>
                {{comment.text}}
            </v-card-text>
            </v-card>
        </v-col>
        </v-row>
    </div>
</template>

<script>
export default {
    props: {
        comments:Array,
    },
    data: () => ({
    inputText: '',
    showError: false,
    localcomments: [],
    }),

    mounted () {
    this.localcomments = this.comments
    },

    methods: {
    addComment() {
        //add comment
        if(this.inputText != ''){
        this.localcomments.push({text: this.inputText})
        this.showError = false
        } else {
        this.showError = true
        }

        //reset variable
        this.inputText = ''

        console.log('comment added: ' + this.inputText)
    }
    },
}
</script>

<style>

</style>