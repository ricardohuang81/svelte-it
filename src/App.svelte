<script>
	import ContactCard from './ContactCard.svelte';

	let name = 'Rico';
	let jTitle = '';
	let description = '';
	// let image = 'https://www.alltalksnewsnetwork.com/wp-content/uploads/2018/11/Boruto_Artucle-900x500.jpg';
	let image = '';
	let age = 38;

	$: uppercaseName = name.toUpperCase();
	$: console.log(name);
	$: if (name === "Ricardo Baby") {
		age = 52;
	}

	function incrementAge() {
		age++;
	}
	function changeName() {
		name = "Ricardo Baby";
	}
	function inputName(event) {
		const enteredValue = event.target.value;
		name = enteredValue;
	}
</script>

<style>
	h1 {
		color: #00CED1;
	}
</style>

<h1>Hola {uppercaseName}! You {age}-year old freak!</h1>
<button on:click="{incrementAge}">Change Age</button>
<!-- <button on:click="{changeName}">Change Name</button> -->
<!-- <input type="text" value="{name}" on:input="{inputName}"> -->
<input type="text" bind:value="{image}">
<input type="text" bind:value="{name}">
<input type="text" bind:value="{jTitle}">
<textarea name="3" bind:value="{description}"></textarea>

<ContactCard
	userImg="{image}"
	userName="{name}"
	jobTitle="{jTitle}"
	{description}
	/>
<!-- {description} is shortcut if variables in App and ContactCard are both "description" -->