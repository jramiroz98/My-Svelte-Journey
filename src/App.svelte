<script>
	let name = 'Jose';
	let age = 24;

    // let uppercaseName; is not required
    $: uppercaseName = name.toUpperCase();

	function incrementAge() {
		age += 1;
	}
    function changeName() {
        name = "Jose Ramiro";
    }
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}, my age is {age + 1}!</h1>
<button on:click="{incrementAge}">Change Age</button>
<button on:click="{changeName}">Change Name</button>
