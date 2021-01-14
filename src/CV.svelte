<script>
 export let title = 'MC'
 export let person

</script>

<h3>{title}</h3>
<h1>{person.name}</h1>
{#each person.skills as skill}
  <div>Skill: {skill.name} Level: {skill.level}</div>
{/each}
