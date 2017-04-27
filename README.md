**Functional Programming in JavaScript:**

**- Why?**
  - Less bugs because it will be easier to reason about.
  - Less time because more re-use of code.

In all functional programmin languagess, functions are values

Divide your code in smaller simpler functions and *compose* them together using higher-order functions.

A higher order funtion is a function that takes another function as an argument.
Examples:

    let orders = [
      1340,
      600,
      345,
      1230,
      3456,
      12345
    ]

**Array.filter:** Iterates over an array and *returns a new array of those items* for which the provided funtion returns true
    Provided functions should return true/false ideally based on some codtion applied on array item.

    // Syntax: filter(function(item, index, object) {
    //   ...code...
    // })

    // Get orders that are multiple of 10
    orders.filter((x) => x % 10 === 0)


**Array.map:** Iterates over an array and *returns a new array* on which provided funtion has performed some operation
    Provided functions should ideally perfrom some desired operation on the array item and return the new value.

    // Syntax: map(function(item, index, object) {
    //   ...code...
    // })

    // Get all orders in float values
    orders_float = orders.map((x) => x.toFixed(2))

**Array.reduce:** Iterates over an array and returns a single value that is obtained by applying a function against each value *and an accumulator*

    // Syntax: reduce(function(accumulator, item, index, object) {
    //   ...code...
    // }, startValueOfAccumulator)

    // Get sum of all values
    orders.reduce((acc, x) => acc + x, 0)

  Advanced example use of Reduce:

    // Group animals by species
    let animals = [
      {name: 'A', species: 'dog'},
      {name: 'B', species: 'dog'},
      {name: 'C', species: 'cat'},
      {name: 'D', species: 'rat'},
      {name: 'E', species: 'bat'},
      {name: 'F', species: 'cat'},
    ]

    let res = animals.reduce((species_group, animal) => {
      species_group[animal.species] = species_group[animal.species] || []
      species_group[animal.species].push(animal.name)
      return species_group
    }, [])

    console.log(res)

**Source:**
- Mattias Petter Johansson - Functional programming in JavaScript - Youtube Playlist
- Link: https://www.youtube.com/playlist?list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84
