<script>
 export let title = 'MC'
 export let person

</script>

<h3>{title}</h3>
<h1>{person.name}</h1>

{#each person.skills as skill}
  <div>Skill: {skill.name} 
     Level: {skill.level}
    {#if skill.level == 5}
    REALLY GOOD
    {:else if skill.level == 4}
    GOOD
    {:else}
    DECENT
    {/if}
  </div>
{/each}
