
<script>
  import CV from './CV.svelte'
  import HttpDemo from './HttpDemo.svelte'


  function handleNewSkill(newSkill) {
    const { detail: { skill, level } } = newSkill;
    person.skills = [...person.skills, { name: skill, level }];
  }

  let person = {
    name: 'Tankred',
    skills: [
      {
        name: 'Svelte',
        level: 5
      },
      {
        name: 'Javascript',
        level: 5
      },
      {
        name: 'Security',
        level: 5
      }
    ]
  }

</script>

<main>
	<CV person={person} on:newSkill={handleNewSkill} />
	<h1>Hello {person.name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<HttpDemo /> 
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
