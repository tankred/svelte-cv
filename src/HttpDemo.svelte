<script>
  let promise = getData();

  async function getData() {
    const response = await fetch('http://api.open-notify.org/astros.json');
    const json = await response.json();
   // ?({"message": "success", "number": 7, "people": [{"craft": "ISS", "name": "Sergey Ryzhikov"}, {"craft": "ISS", "name": "Kate Rubins"}, {"craft": "ISS", "name": "Sergey Kud-Sverchkov"}, {"craft": "ISS", "name": "Mike Hopkins"}, {"craft": "ISS", "name": "Victor Glover"}, {"craft": "ISS", "name": "Shannon Walker"}, {"craft": "ISS", "name": "Soichi Noguchi"}]}) 

const studentDetails =[
   {
      name : "John"
   },
   {
      name : "David"
   },
   {
      name : "Bob"
   }
];
const ListOfStudentName =
studentDetails.map(({name:actualValue})=>actualValue);
console.log(ListOfStudentName);

    return ListOfStudentName
  }
  
</script>

<style>
  .row {
    margin: 10px;
    box-shadow: 0 0 5px gray;
    padding: 10px 20px;
  }

  .error {
    background: lightcoral;
    border: solid 1px red;
    padding: 10px 20px;
  }
</style>

{#await promise}
 <p>...loading</p>
 {:then data}
 <div>
     {#each data as row}
     <div class="row">{row}</div>
   {/each}
</div>
 {:catch error}
 <div class="error">
   Something went wrong {error.message}
 </div>
{/await}
