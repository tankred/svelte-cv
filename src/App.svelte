
<script>
  import CV from './CV.svelte'
  import HttpDemo from './HttpDemo.svelte'

  export let name;

  let newSkill = '';
  let newSkillLevel = 1;

  function saveSkill() {
    // TODO save skill
    console.log('saving skill', newSkill, newSkillLevel);
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
	<CV person={person} />
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<HttpDemo /> 

<h2>Add skill</h2>
<div>
  <input bind:value={newSkill} placeholder="skill name">
  <input bind:value={newSkillLevel} type="number" min="1" max="5" />
  <button on:click={saveSkill} >Save</button>
 </div>

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
