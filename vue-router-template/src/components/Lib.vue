<template>
	<div class="container">
		<div class="side-bar">
			<router-link to="/title_lib">题库</router-link>
			<router-link to="/resourse_lib">资源库</router-link>
			<router-link to="/action_lib">活动库</router-link>
		</div>
		<div class="content"><router-view /></div>
	</div>
</template>

<script>
export default {
	name: 'Lib',
	data() {
		return {
			
		};
	}
};
</script>

<style>
</style>
