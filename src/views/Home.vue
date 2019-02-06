<!-- Template -->
<template>
  <div class="home">
    <Skilltree/>
  </div>
</template>

<!-- Script -->
<script lang="ts">
	import { Component, Vue } from 'vue-property-decorator';
	import Skilltree from '@/components/Skilltree.vue';

	@Component({
	  components: {
	    Skilltree
	  },
	})
	export default class Home extends Vue {}
</script>

<!-- Style -->