# Natural selection
A brief simulation about Darwin's Natural Selection


The project started with an idea of simulate a biological system where natural selection happens. The main idea was make animals that can reproduce and die, and see what happen when some of them have some genetical factors that give them some advantages.

So, to do this we have to consider two genetic characteristics to the individuals, the capacity of hind from the predator(camouflage chance) and the capacity of have childs(birth chance). So the ones with low camouflage will die, and the ones with high camouflage will live, and pass the "good-genes" to the next generations.

But, we have to "creat the time" where an action can be, I made a turn system, for example, I have a 90% chance to make a child, so I will make it in X turns, the eficience of make a child is equivalent of how much turns it takes to creat a new individual.

In each turn, each individual can die, or survive, it depends on the camouflage of the individual.

But, what's the algorithm to define how much of these factors the child will have? Well, it depends on the father of him.

First of all, we have to define the factors that the child will have, camouflage and eficience(birth chance)

But, these factors can be better, or worse than his father's factors.

So, the first step is make a binary chance of the characteristics increase or decrease

The second step is think, ok it will be better/worse, but how much? so we have to create a percentual chance to define how good or how bad it will be, it's just a question of add or subtract it from the father's factor

Ok, now we have a new individual with his own factors, now we have to make a algorithm to decide wich individuals will die, and wich individuals will live, it's just  question of camouflage

It's simple, just creat a ...
