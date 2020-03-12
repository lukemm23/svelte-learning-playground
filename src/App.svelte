<script>
  let name = "luke";
  let age = 36;

  $: uppercaseName = name.toUpperCase();

  $: console.log(name);

  $: if (name === "Lucas") {
    console.log("it runs");
    age = 31;
  }

  function incrementAge() {
    age += 1;
  }

  function changeName() {
    name = "Lucas";
  }

  function nameInput(event) {
    const enteredValue = event.target.value;
    name = enteredValue;
  }
</script>

<style>
  h1 {
    color: black;
  }
</style>

<!-- you could input simple javascript methods inside and between curly brackets -->
<h1>Hello {uppercaseName}! My age is {age}!</h1>
<button on:click={incrementAge}>Change Age</button>
<button on:click={changeName}>Change Name</button>

<!-- 2 directional data flow for input -->
<!-- solution 1 (long way) -->
<!-- <input
  type="text"
  placeholder="Enter Your Name"
  value={name}
  on:input={nameInput} /> -->

<!-- solution 2 (shortcut) -->
<!-- not good to abuse this, but for inputs they are good -->
<input type="text" bind:value={name} />
