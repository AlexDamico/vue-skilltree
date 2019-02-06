<template>
    <div id="skilltree">
        <h1>SKILL TREE</h1>

        <Skill v-for="skill in skills" v-bind:skill="skill" v-bind:key="skill.key" />

        <div><button @click="reset">Reset Skill Points</button></div>
    </div>
</template>

<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';
    import Skill from "./Skill.vue";

    @Component({
        components: {
            Skill
        }
    })
    export default class Skilltree extends Vue {
        // skill: number = 0;

        get skills() {
            return this.$store.state.skills;
        }

        reset() {
            // this.skill = 0
        }
    }
</script>

<style lang="scss" scoped>
    
</style>
