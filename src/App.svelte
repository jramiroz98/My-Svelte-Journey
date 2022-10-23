<script>
  import ContactCard from "./ContactCard.svelte"

  let name = "Jose"
  let age = 24
  let image = ""
  let jobTitle = "Engineer"
  let description = "fucking awesome"

  // let uppercaseName; is not required
  $: uppercaseName = name.toUpperCase()

  $: console.log(name)

  $: if (name === "Jose Ramiro") {
    console.log("It runs!")
    age = 31
  }

  function incrementAge() {
    age += 1
  }
  function changeName() {
    name = "Jose Ramiro"
  }
  function nameInput(event) {
    const enteredValue = event.target.value
    name = enteredValue
  }
</script>

<h1>Hello {uppercaseName}, my age is {age}!</h1>
<button on:click={incrementAge}>Change Age</button>
<!-- <button on:click="{changeName}">Change Name</button> -->
<!-- <input type="text" value="{name}" on:input="{nameInput}"> -->
<input type="text" bind:value={name} />
<input type="text" bind:value={jobTitle} />
<input type="text" bind:value={image} />
<textarea rows="3" type="text" bind:value={description} />

<ContactCard userName={name} {jobTitle} {description} userImage={image} />

<style>
  h1 {
    color: purple;
  }
</style>
