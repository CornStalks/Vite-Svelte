<script>

let test1 = 0

let randomnumber = 0

let children_in_basement = 0

function add_a_child(){
children_in_basement +=1
}
function kill_a_child(){
children_in_basement -=1
}

function test(){
  test1 +=1
}

let YourName = "" // Btw doulbe quotes ("") is a string!
</script>

<input type="text" bind:value={YourName} placeholder="Your Name"/>
<input type="number" bind:value={children_in_basement} min="0" max="100" />
<input type="range" bind:value={randomnumber} min="-100" max="100" />
<input type="number" bind:value={randomnumber}/> 
 
<!-- Idk why this wierd comment symbols are here, that's how html does it ig smh... But anyways...
There are many different types of inputs. there are checkboxes as well as other stuff!-->

<h1> 
Hello {YourName}. This is a level one heading
</h1>

<p>This is a paragraph</p>

<h2> This is a level two heading </h2>

<style> 
h1 {

background: red

}
</style>

<p> Put a child in your basement: </p>
<p>Number of Children: {children_in_basement} </p>


<button on:click={add_a_child}>

Add one child to your basement</button>

<button on:click={kill_a_child}>

Free a child (why would u?) </button>

<button on:click={test}