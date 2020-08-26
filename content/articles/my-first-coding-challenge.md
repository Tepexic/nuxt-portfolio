---
title: My first coding challenge while job hunting
description: A JavaScript function that takes a non-negative number of bytes and returns a string with the equivalent number of kB, MB, GB, TB, PB, EB, ZB, or YB
img: "https://images.unsplash.com/photo-1550645612-83f5d594b671?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80"
alt: My first coding challenge while job hunting
tags: ['webdev', 'JavaScript']
author: 
  name: Jesus Velazquez
  bio: Pro Stack Overflow copy-paster
  img: images/avatar.png
---
# My first coding challenge while job hunting
After several failed attempts to land a coding interview, they finally called me. They went with me over my CV and my previous experience with JavaScript on the phone, and I was just really nervous, but I thought I did fine.

A couple of days later, I got an email with a small coding challenge. But it didn't matter that it was small, it was my first real one. Now, I've tried my hand at some coding challenges before ([here are my solutions to a few Project Euler problems](https://github.com/Tepexic/project-euler-solutions)), but I've never had an *actual* coding challenge for an interview.

Here's what I had to do:

*Write a function in JavaScript called ‘humanSize’ that takes a non-negative number of bytes and returns a string with the equivalent number of ‘kB’, ‘MB’, ‘GB’, ‘TB’, ‘PB’, ‘EB’, ‘ZB’, or ‘YB’, between [0, 1000), with at most 1 digit of precision after the decimal. If the number of bytes is >= 1000 YB, return this number of YB, for example 5120 YB. For example, your function might return ‘107.3MB’. Write this function without writing a separate case for each byte prefix, and without using Math.log or Math.pow.*

## The planning
The first thing I though was: this will need testing. I needed to write some tests to check that the function was actually doing what I wanted it to do, and the best approach would be using Test Driven Development (TDD). This way I could show that I knew how to test my code and I could plan ahead. I also wanted to set up a GitHub Repo to store all of this.

## The algorithm
I was certain I needed tests. But I still had no clear idea on how to get it done. So I took my pencil and my notebook and scribbled a flowchart.

The idea behind was simple: I was to have a dictionary for the prefixes, this was easier to do than a *switch-case* statement, or several *if-elses*, and, I was not allowed to use them anyway. This dictionary needed a *"pointer"*, a way to tell how many times had I divided by 1000.

I also needed a loop, a way to constantly divide the input (number of bytes) by 1000, until its integer part was 0, that meant I had reached the maximum times of divisions by 1000,an thus, I had a number to show. The dictionary pointer needed to increase at every run of the loop, and the loop was to run at least once, to check if a had something at least in a size of *kB*.

The problem statement had another restriction: *If the number of bytes is >= 1000 YB, return this number of YB*. This meant that whenever I had divided by 1000 more than 8 times, I had reached the line of thousands of yottabytes. I came into this conclusion by looking up how many zeros there are in a yottabyte. Turns out the factor is 10²⁴, so 24/3 = 8. This was to be a condition within my loop.

If the loop was broken by this last condition, the function had to return the rounded number of yottabytes. Otherwise, return the rounded number to 1 decimal place and concatenate it as a string to the dictionary prefix extracted by the pointer.

After some iterations, I had this:
![Algorithm flowchart](https://tepexic.com/assets/blog/my-first-coding-challenge/chalk-diagram.png)

I wasn't planning on error handling here, I thought that was best left to the coding part. But I wanted the function to return *'0kB'* if the input was not valid.

## The tests
I decided to go with TDD on this one, so the first thing to to is write the Tests. By this point, I already knew 2 things: what the function had to do and how was it going to do it.

I started a new Node project inside my */human-size/* folder by running

```javascript[]
npm init -y
```

The idea behind each test was to provide a number of bytes and compare the output of the function to what I already knew the conversion value was. I'm familiar with [Jest](https://jestjs.io/), so I had to install it first.

```javascript[]
npm install --save jest
```

Then my first test was:

```javascript[humanSize.spec.js]
test("Should return 3.1kB", () => {
    expect(humanSize(3125)).toBe("3.1kB");
  });
```
Given 3125B, I knew this was 3.125kB, but, by definition, I was to round that number to 1 decimal place, hence *3.1kb*

Then I went a bit picky and wrote the tests for an invalid input, such as a _String_, _NaN_, _Object_, _Array_ or simply a negative number:

```javascript[humanSize.spec.js]
test("Should return 0kB when input is String", () => {
    expect(humanSize("asd")).toBe("0kB");
  });

  test("Should return 0kB when input is NaN", () => {
    expect(humanSize(NaN)).toBe("0kB");
  });

  test("Should return 0kB when input is Object", () => {
    expect(humanSize({ a: "foo", b: 123 })).toBe("0kB");
  });

  test("Should return 0kB when input is Array", () => {
    expect(humanSize([200, 100])).toBe("0kB");
  });

  test("Should return 0kB when input is <0", () => {
    expect(humanSize(-25)).toBe("0kB");
  });
```

From this point onwards, the test should be focused on ensuring the correct output. So I wrote a test for every prefix:

```javascript[humanSize.spec.js]
test("Should return 31.3kB", () => {
    expect(humanSize(31250)).toBe("31.3kB");
  });

  test("Should return 31.3MB", () => {
    expect(humanSize(31250000)).toBe("31.3MB");
  });

  test("Should return 31.3GB", () => {
    expect(humanSize(31250000000)).toBe("31.3GB");
  });

  test("Should return 31.3TB", () => {
    expect(humanSize(31250000000000)).toBe("31.3TB");
  });

  test("Should return 31.3PB", () => {
    expect(humanSize(31250000000000000)).toBe("31.3PB");
  });

  test("Should return 31.3EB", () => {
    expect(humanSize(31250000000000000000)).toBe("31.3EB");
  });

  test("Should return 31.3ZB", () => {
    expect(humanSize(31250000000000000000000)).toBe("31.3ZB");
  });

  test("Should return 31.3YB", () => {
    expect(humanSize(31250000000000000000000000)).toBe("31.3YB");
  });
```

And finally, test for the thousands of YB case:

```javascript[humanSize.spec.js]
test("Should return 3125YB", () => {
    expect(humanSize(3125000000000000000000000000)).toBe("3125YB");
  });
```

Now I added the test script to my *package.json*:
```javascript[package.json]
"scripts": {
    "test": "jest",
  },
```

## The code
I decided to focus on the invalid cases first. If we operate on something that is not a number (let's not count string concatenation), we would get a *NaN*. So I did that, and also added another check for negative numbers:

```javascript[humanSize.js]
function humanSize(b) {
    // default return when input is not valid
    const def = "0kB";
    // Parse input
    if (isNaN(b / 1000)) return def;
    if (b < 0) return def;
  }

  module.exports = humanSize;
```

This will pass the invalid input tests, but fail all others. In TDD, this is the right track.

Now it's time to translate the flowchart into code. The first part is the dictionary and the initialization of variables
```javascript[humanSize.js]
function humanSize(b) {
    // default return when input is not valid
    const def = "0kB";
    // Parse input
    if (isNaN(b / 1000)) return def;
    if (b < 0) return def;
    // Prefix hash
    const prefix = {
      1: "k",
      2: "M",
      3: "G",
      4: "T",
      5: "P",
      6: "E",
      7: "Z",
      8: "Y",
    };
    // Prefix pointer/counter
    var i = 0;
    // Initialize size variable
    var B = b;
  }

  module.exports = humanSize;
```

Good, now I needed the loop. Notice I set up the first index of my dictionary to 1, and my pointer starts at 0. I did this because I needed to know if the number of bytes was at least on the range of *kB*, that means, the loop has to run at least once. This led me into a Do While statement.

```javascript[humanSize.js]
function humanSize(b) {
    // default return when input is not valid
    const def = "0kB";
    // Parse input
    if (isNaN(b / 1000)) return def;
    if (b < 0) return def;
    // Prefix hash
    const prefix = {
      1: "k",
      2: "M",
      3: "G",
      4: "T",
      5: "P",
      6: "E",
      7: "Z",
      8: "Y",
    };
    // Prefix pointer/counter
    var i = 0;
    // Initialize size variable
    var B = b;
    // Iterate over the size variable until its integer part is 0
    do {
      if (i > 7) return Math.round(B.toString()) + prefix[8] + "B";
      i += 1;
      B /= 1000;
    } while (Math.trunc(B / 1000) > 0);
  }

  module.exports = humanSize;
```

I also included the check for thousands of *YB*, it'll break the loop and return the rounded number of YB. Now the only thing missing was to round the number to 1 decimal place for all other cases. A quick search on [30 Seconds of Code](https://www.30secondsofcode.org/) gave me a snippet called simply *round*, that returns a number rounded to a specified number of decimals:

```javascript[]
const round = (n, decimals = 0) => Number(`${Math.round(`${n}e${decimals}`)}e-${decimals}`);
```

So I embeded that into my `humanSize(b)` function, followed by the prefix:

```javascript[humanSize.js]
function humanSize(b) {
    // default return when input is not valid
    const def = "0kB";
    // Parse input
    if (isNaN(b / 1000)) return def;
    if (b < 0) return def;
    // Prefix hash
    const prefix = {
      1: "k",
      2: "M",
      3: "G",
      4: "T",
      5: "P",
      6: "E",
      7: "Z",
      8: "Y",
    };
    // Prefix pointer/counter
    var i = 0;
    // Initialize size variable
    var B = b;
    // Iterate over the size variable until its integer part is 0
    do {
      if (i > 7) return Math.round(B.toString()) + prefix[8] + "B";
      i += 1;
      B /= 1000;
    } while (Math.trunc(B / 1000) > 0);
    // Return size rounded to 1 decimal with correspoding prefix
    return (
      Number(`${Math.round(`${B}e${1}`)}e-${1}`).toString() + prefix[i] + "B"
    );
  }

  module.exports = humanSize;
```

This function is now passing all the tests, and, believe me, that is one of the best feelings in the world.


## Final remarks
That was it. The only thing left was to create a `.gitignore` to avoid pushing the */node_modules* folder to the GitHub repository. 

They asked me to submit the function inside a GitHub gist, so I did. I'm waiting for their response now. I'll update as soon as I know anything :)

[Here's the repo of this code](https://github.com/Tepexic/human-size).