<script>
let e = 0
function placeholder(){
e -= 1
}

//This is for Electron Clicker//
let AutoClicker = 0
let Protoncost = 50
let Nuetroncost = 500
let Nuetronprotoncost = 5
let Electron = 0
let Proton = 0
let Nuetron = 0
let Oxygen = 0
let Oxygencost = 8000
let Oxygenprotoncost = 5
let Oxygennuetroncost = 5

$: Electronperclick = 1 + 0.5 * Proton + 2 * Nuetron + 15 * Oxygen

function devtools(){
Electron += 100000000
}

function range(max) {
  return Array(max).fill()
}

setInterval(Autolicker, 33399999999999999)

function Autolicker(){
  for (const _ in range(Autolicker)) {
    click()
  }
}

function click(){
  Electron = (((Electron) + Electronperclick) *100) /100 
}

function buyProton(){
if(Electron >=~~Protoncost){
  Electron -= ~~Protoncost
Protoncost *= 1.1
Proton += 1
}
}

function buyNuetron(){
  if(Electron >=Nuetroncost , Proton >=Nuetronprotoncost){
   Proton -= ~~Nuetronprotoncost
    Electron -= ~~Nuetroncost
    Nuetroncost *= 1.1
    Nuetronprotoncost *= 1.1
    Nuetron += 1
  }
}

function buyOxygen(){
  if(Electron >=Oxygencost , Proton >=Oxygenprotoncost , Nuetron >=Oxygennuetroncost){
    Proton -= ~~Oxygenprotoncost
    Electron -= ~~Oxygencost
    Nuetron -= ~~Oxygennuetroncost
    Oxygen += 1
  }
}




//This is for other sturf//
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

function less(){
  test1 -=1
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

<p>{test1}</p>

<button on:click={test} on:contextmenu|preventDefault={less}>
No 
</button>

<p></p>
<!--This next section is all for Electron Clicker-->

<button on:click={devtools} on:contextmenu|preventDefault={less}>
Devtools
</button>

<p>Electrons Per Click: {Electronperclick.toFixed(1)}   </p>

<button on:click={click} on:contextmenu|preventDefault={placeholder}>
Electrons: {Electron.toFixed(1)} <p></p>
Protons: {Proton.toFixed(1)} <p></p>
Nuetrons: {Nuetron.toFixed(1)}
</button>

<p></p>

<button on:click={buyProton} on:contextmenu|preventDefault={placeholder}>
Buy Proton
Cost: {~~Protoncost} Electrons
</button>

<button on:click={buyNuetron} on:contextmenu|preventDefault={placeholder}>
Buy Nuetron
Cost: {~~Nuetroncost} Electrons, {~~Nuetronprotoncost} Protons

</button>

<button on:click={buyOxygen} on:contextmenu|preventDefault={placeholder}>
Buy Oxygen
Cost: {~~Oxygencost} Electrons, {~~Oxygenprotoncost} Protons, {~~Oxygennuetroncost} Nuetrons
</button>