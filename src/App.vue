<template>
	<div id="app">
		<div id="nav">
			<router-link to="/">Home</router-link>|
			<router-link to="/about">About</router-link>|
			<router-link to="/arya-list">Arya's List</router-link>
		</div>
		<router-view/>
	</div>
</template>

<style lang="scss">
.ml10 {
	margin-left: 10px;
}
.mr10 {
	margin-right: 10px;
}
.mr20 {
	margin-right: 20px;
}
.mt10 {
	margin-top: 10px;
}
.mb20 {
	margin-bottom: 20px;
}
#app {
	font-family: "Avenir", Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
}
#nav {
	padding: 30px;
	a {
		font-weight: bold;
		color: #2c3e50;
		&.router-link-exact-active {
			color: #42b983;
		}
	}
}
</style>
