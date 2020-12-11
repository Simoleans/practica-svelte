<script>
	import About from "./component/About.svelte";
	import Text from "./component/Text.svelte";
	import Person from "./component/Person.svelte";
	import Skills from "./component/Skills.svelte";
	import Input from "./component/Input.svelte";
	import Photos from "./component/Photos.svelte";
	import ButtonCount from "./component/ButtonCount.svelte";

	export let name;
	export let lastName; 

	 let svelteLogo = "logo/logo.png"

	 const data = {
	 	name : "Fran",
	 	lastName : "Hernandez",
	 	age : 27,
	 	rrss : '@futfran'

	 }
</script>

<main>
	<h1>Hello {name} {lastName}!</h1>
	<About />
	<Text anotherText="Hola!"/>
	<Text />
	 <!-- se puede poner sin el attr name si la variable se llama igual-->
	<!-- <Person name={data.name} lastName={data.lastName} age={data.age} rrss={data.rrss} /> -->
	<!-- otra forma-->
	<Person {...data} />
	<Skills />
	<Input />
	<Photos />
	<ButtonCount />
	<img src={svelteLogo} alt="Svelte">
</main>

<style>
	/*	stilos globales */
	:global(body) {
		background-color: #f2eee2;
		color: skyblue;
	}

	:global(body.dark-mode){
		background-color: #1d3040;
		color : #bfc2c7;
	}

	/*variables css */
	:global(:root){
		--theme-color: purple;
	}

	main img{
		width: 30%;
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>