<template>
    <button class="skill"
        @click="addPoint" 
        v-bind:class="{ maxed: skill.points === skill.skillCap }">

        <span class="points">{{skill.points}}</span>

        <div class="tooltip">
            <h3>{{skill.name}}</h3>
            <h4>Rank {{skill.points}}/{{skill.skillCap}}</h4>
            <p>{{skill.description}}</p>
        </div>
    </button>
</template>

<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';

    @Component({
        props: {
            skill: Object
        }
    })
    export default class Skill extends Vue {
        skill: any = this.skill;

        addPoint() {
            this.skill.points++;
        }
    }
</script>

<style scoped lang="scss">
    button.skill {
        position: relative;
        width: 50px;
        height: 50px;
        margin: 5px;
        color: white;
        background: black;
        border: 1px solid lime;
        border-radius: 5px;
        cursor: pointer;
        &:hover {
            box-shadow: 0 0 15px inset lightskyblue;
            div.tooltip { display: block; }
        }
        &.maxed {
            border-color: goldenrod;
            pointer-events: none;
            span.points { color: goldenrod }
        }
        span.points {
            position: absolute;
            right: -8px;
            bottom: -8px;
            width: 8px;
            padding: 1px 2px;
            color: lime;
            background: black;
            border: 1px solid goldenrod;
            border-radius: 5px;
        }
        div.tooltip {
            display: none;
            position: absolute;
            left: 0;
            bottom: 0;
            width: 300px;
            padding: 0 8px;
            color: white;
            background: rgba(12, 12, 69, 0.9);
            text-align: left;
            border: 1.5px solid lightgray;
            border-radius: 5px;
            transform: translate(52px, -52px);
            h3, h4, p { margin: 5px 0; font-size: 0.8rem; }
            p { color: goldenrod; }
        }
    }
</style>

