<template>
    <div>
        <h2 class="headline font-weight-bold mb-3" >
            {{likes}}
            </h2>

            <v-row justify="center">
            <v-col cols="4" class="mx-auto">
                <v-btn
                    class="mx-2"
                    fab
                    dark
                    small
                    color="pink"
                    v-on:click="addLike"
                >
                    <v-icon dark>
                    mdi-heart
                    </v-icon>
                </v-btn>

            </v-col>
            </v-row>
    </div>
</template>

<script>
export default {
    props: {
        likes:Number,
    },

    methods: {
        addLike() {
        this.$emit('incrementParentLikes')
        },
    },

}
</script>
<style>

</style>