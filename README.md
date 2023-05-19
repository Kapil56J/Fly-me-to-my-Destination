# Fly-me-to-my-Destination

Here is the Answer of above question.

function minimumPlanesNeeded(fuel) {
  let planesNeeded = 0; // Variable to keep track of the minimum number of planes needed
  let currentFuel = fuel[0]; // Initialize the current fuel to the fuel at the starting airport

  for (let i = 1; i < fuel.length; i++) {
    // Iterate through the fuel array starting from the second element

    if (currentFuel < 1) {
      // If the current fuel is less than 1, it means you cannot reach the next airport
      planesNeeded++; // Hire a new plane
      currentFuel = fuel[i]; // Set the current fuel to the fuel value of the current airport
    } else {
      currentFuel--; // Subtract 1 from the current fuel since you use 1 unit of fuel to fly to the next airport
    }
  }

  if (currentFuel < 1) {
    // After the iteration, if currentFuel is less than 1, it means you cannot reach the last airport
    return -1; // Return -1 to indicate it is not possible to reach the last airport
  } else {
    planesNeeded++; // Increment planesNeeded by 1 to account for the last flight to the last airport
    return planesNeeded; // Return the minimum number of planes needed
  }
}

const fuelArray = [2, 1, 2, 3, 1];
const result = minimumPlanesNeeded(fuelArray);
console.log(result);
