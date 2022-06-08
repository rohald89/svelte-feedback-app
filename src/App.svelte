<script>
  const firstName = "Rohald";
  const lastName = "van Merode";
  let color = "blue";
  let showText = false;
  let users = [
    {
      id: 1,
      name: "John",
      age: 20,
    },
    {
      id: 2,
      name: "Jane",
      age: 21,
    },
    {
      id: 3,
      name: "Bob",
      age: 22,
    },
  ];

  $: name = firstName + " " + lastName;

  const toggle = () => {
    color = color === "blue" ? "red" : "blue";
    showText = !showText;
    users = [...users, { id: users.length + 1, name: "New user", age: 23 }];
  };
</script>

<main>
  <h1 style="color:{color}">Hello {name}!</h1>

  {#if showText}
    <p>
      Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
      how to build Svelte apps.
    </p>
  {:else}
    <p>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Repudiandae
      obcaecati tempora neque accusantium sed labore debitis similique iure.
      Molestiae, voluptatem. Distinctio ex mollitia minus praesentium cum
      repellat consequuntur ab! Amet.
    </p>
  {/if}

  <button on:click={toggle}>Click</button>

  {#each users as user (user.id)}
    <p>{user.name} is {user.age} years old.</p>
  {/each}
</main>

<style>
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
