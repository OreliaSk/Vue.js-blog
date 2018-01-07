<template>
	<nav>
		<ul>
			<li>
				<router-link to="/" exact>Blog</router-link>
			</li>
			<li>
				<router-link to="/add" exact>Add a New Blog</router-link>
			</li>
		</ul>
	</nav>
</template>


<style scoped>

ul{
    list-style-type: none;
    text-align: center;
    margin: 0;
}
li{
    display: inline-block;
    margin: 0 10px;
}
a{
    background: rgba(68, 68, 68, 0.7);
    color: #fff;
    text-decoration: none;
    padding: 12px;
    border-radius: 5px;
}
nav{
    background: url(../assets/Header/header-background.jpg) center;
    padding: 40px 0;
}
.router-link-active{
    background: #444;
    color: rgba(255,255,255,0.9);
    box-shadow: 2px 2px 2px #000;
}
	
</style>