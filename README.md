Download Link: https://assignmentchef.com/product/solved-cs2030s-lab-0-circle-and-points
<br>
Estimating Pi using Monte Carlo Method

The Monte Carlo method for estimating the value of pi is asfollows.  We have a square of width 2r, and within it, acircle with a radius of r.

We randomly generate k points within the square.  We counthow many points fall within the circle.  Suppose n pointsout of k fall within the circle.

Since the area of the square is 4r^2 and the area of thecircle is pi r^2, the ratio between them is pi/4.  The ration/k should therefore be pi/4, and pi can be estimated as4n/k.

### Background: Random Number Generator

To estimate pi using the method above, we need to use arandom number generation.  A random number generator is anentity that spews up one random number after another.  We,however, cannot generate a truly random numberalgorithmically.  We can only generate a pseudo-randomnumber.  A pseudo-random number generator can be initializedwith a seed.  A pseudo-random number generator, wheninitialized with the same seed, always produces the samesequence of (seemingly random) numbers.

Java provides a class `java.util.Random` that encapsulates apseudo-random number generator. We can create a randomnumber generator with a seed:

“`Random rng = new Random(1);“`

We can then call `rng.nextDouble()` repeatedly to generaterandom numbers between 0 and 1.

Using a fixed seed is important for testing since theexecution of the program will be deterministic, even whenrandom numbers are involved.

## Files Provided

In this directory, you should see the following files:

– Skeleton Java files: `Point.java`, `RandomPoint.java`,`Circle.java`, `Lab0.java`

– Inputs and outputs for `Lab0`: `inputs/Lab0.k.in` and`outputs/Lab0.k.out` for different values of k.

– Bash script: `test.sh` for testing `Lab0` if it estimatespi correctly, by comparing the output when running `Lab0` on`inputs/Lab0.k.in` to the expected output in`outputs/Lab0.k.out`

– Unit tests for Java classes: `Test.java`.  This file testsindividual classes to check if they have the expectedbehavior

## Your Task

A skeleton code has been given.  Your task is to completethe implementation of the classes `Point`, `RandomPoint`,`Circle`, and `Lab0`, according to the OO principles thatwere taught: abstraction, encapsulation, information hiding,inheritance, tell-don’t-ask.

Another client class `Test` is given to test the behavior ofyour code.  You are required to pass the test cases given in`Test`.

## `Circle`

Most of the `Circle` class has been written for you.  Youneed to complete the method `contains`.

## `Point`

You need to fill in the class `Point` with the constructor,`toString`, and any other methods necessary.

## `RandomPoint`

`RandomPoint` is a subclass of `Point` that represents arandomly generated point.  The random number generator thatgenerates a random point has a default seed of 1.  There isa public method `setSeed()` that we can use to update theseed.

This is how it can be used.

To generate a new point,“`Point p = new RandomPoint(minX, maxX, minY, maxY);“`

`minX`, `minY`, `maxX`, `maxY` represent the minimum andmaximum possible x and y values respectively, for eachrandomly generated point.

To set the random seed,“`RandomPoint.setSeed(10);“`

Tips: What are the fields and methods that should beassociated with the class `RandomPoint` instead of aninstance of `RandomPoint`?

### Lab0

`Lab0` is the main program to solve the problem above.  The`main` method is provided.  It includes the method to readin the number of points and the seed from the standard inputand to print the estimated pi value.

The method `estimatePi` is incomplete.  Determine how youshould declare `estimatePi`, then complete the body bygenerating random points and count how many fall under thegiven circle.

Use r = 0.5 and use `long` and `double` within `estimatePi`to ensure you have the right precision.

To run `Lab0` and enter the input manually, run“`java Lab0“`

The program will pause, waiting for inputs from keyboards.Enter two numbers. The first is the number of points. Thesecond is the seed.

You can enter the two numbers into a text file, say, `TEST`,and then run“`java Lab0 &lt; TEST“`

Sample inputs and outputs have been provided and can befound under the `inputs` and `outputs` directory.

## Testing

You should test your classes individually before testing`Lab0`.  A simple `Test.java` is given.  You can run it with“`java Test“`

To test your implementation of `Lab0`, automatically againstthe test data given in `inputs` and `outputs`,