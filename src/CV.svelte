<script>
  import { createEventDispatcher } from 'svelte';
  export let title = 'MC'
  export let person

  const dispatch = createEventDispatcher();


  let newSkill = 'ps';
  let newSkillLevel = 1;

  function saveSkill() {
    dispatch('newSkill', {
      skill: newSkill,
      level: newSkillLevel
    });
  }

</script>

<h3>{title}</h3>
<h1>{person.name}</h1>

{#each person.skills as skill}
  <div>Skill: {skill.name} 
     Level: {skill.level}
     {#if skill.level >= 5}
       REALLY GOOD
     {:else if skill.level == 4}
       GOOD
     {:else}
       DECENT
     {/if}
  </div>
{/each}


<h2>Add skill</h2>
<div>
  <input bind:value={newSkill} placeholder="skill name">
  <input bind:value={newSkillLevel} type="number" min="1" max="5" />
  <button on:click={saveSkill} >Save</button>
 </div>
