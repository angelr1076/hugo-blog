---
author: "Angel Rodriguez"
date: 2018-11-26
linktitle: JavaScript Arrays
menu:
  main:
    parent: tutorials
next: /tutorials/github-pages-blog
prev: /tutorials/automated-deployments
title: JavaScript Arrays...
weight: 10
---

## To Start
Today we'll be covering a sample of methods JavaScript offers to iterate through arrays. This article is inspired by a video posted by Andrew Mead in his <a href="https://www.udemy.com/modern-javascript/" target="_blank">Modern JavaScript Bootcamp.</a> This article is recommended for beginners looking to better understand how JavaScript iterates through an array, one item at a time. This is something I had a difficult time with when I first started to learn the language.

MDN Web Docs defines an array as "an ordered collection of data (either primitive or object depending upon the language). Arrays are used to store multiple values in a single variable." An array, in JavaScript, is a housing unit for one to multiple pieces of information. They can store integers, string or sub-arrays(arrays within arrays). Each block item in an array is called an element.

## Arrays in JavaScript
Let's take this holiday prep list in the form of an array, for example. This is what's called an array literal. 
<dd>const prepList = ['chicken', 'turkey', 'duck', 'turducken', 'cranberry sauce'];</dd>

In JavaScript, each array item has its own index number. Arrays always start with an index of 0. To get the index number of an element in a given array, you would take the name of the array, along with the built-in "indexOf" and finally, add the name of the element, in quotes, and wrapped in parenthesis. The "indexOf()" method, like it's name, gives you the index of the array item you've entered in your search:
<dd>prepList.indexOf('chicken'); // result is 0 or the first item in the array</dd>

When you want to reference an element in the array, you simply call the array name, and in brackets, the index number of the element. Let's say we want to grab 'turducken' (If you've never had turducken, add it to your bucket list). We know that turducken is the 4th item in the array, in this case that would be index [3] since the array always begins at index [0].
<dd>prepList[3]; // result is 'turducken'</dd>

## The For Loop

We'll be covering the "for loop", ".forEach()" and the ".map()" built-in methods.

The "for loop" according to MDN Web Docs "repeats until a specified condition or value evaluates to false". The for loop consists of an initial expression; condition; increment expression, in this exact order. It's kind of an antiquated method to iterate through an array, but for the purpose of this lesson, especially for those at the beginning of their JavaScript learning path, it's a bit clearer what's going on while iterating through the array. It's also a bit easier being that you can run the loop a specific number of times.

Again, let's use our prep list as an example: 
<dd>const prepList = ['chicken', 'turkey', 'duck', 'turducken', 'cranberry sauce'];</dd>

We'll use the for loop to iterate through the array, and build a quick numbered list. I'll also use template strings to easily print out the list and avoid the messiness of concatenation. If you haven't heard of template strings or concatenation, I recommend heading to MDN Web Docs. MDN will soon be one of your "go to" sites if you plan on becoming a developer.

<dd>for (let i = 0; i < prepList.length; i++) {</dd>
    <dd>let num = i + 1;</dd>
    <dd>console.log(`${num}. ${prepList[i]}`);</dd>
<dd>}</dd>
</br>
<dd>1. chicken</dd>
<dd>2. turkey</dd>
<dd>3. duck</dd>
<dd>4. turducken</dd>
<dd>5. cranberry sauce</dd>

Let's dissect what's happening here. We're declaring a command to run on a code block (inside the command) a given number of times. In the first statement, we're telling the loop to begin at index 0(let i = 0), in this case, that's 'chicken'. In second statement, we are telling the loop that i is never longer than the prepList length. i < prepList.length is stating, STOP at the last index element of the array. In our final statement, we're telling the loop that each time the code block runs and completes, i++ or add 1 to the index. So if we're at index 2, we have a total of 5 index elements and let's move on to index 3 once the iteration for index 2 is complete. In the code block, we declared a variable called "num". It takes on the the number of times our index is running through prepList.length, but we are adding one to it. The reason why we do this is we want to add a list number to each element, but we wouldn't want our user to see chicken as a item with the number 0 next to it. Plus, our user doesn't know that we're iterating through an array or that arrays begin at the 0 index. So we add one to num and it attaches to the prepList index to display a nice, clean list. Next, we will console log the array number ${num} and add the prepList[i] or element that is being iterated in the code block. So there we have it, that's our first list with the for loop.

## forEach()

ForEach() is a nice way to iterate through objects and arrays. Technically, an array is an object but let's avoid getting into that conversation to avoid confusion. You will better understand this the more you read about JavaScript and its intricacies. With forEach(), we are not creating a new array, like we would with a map() function.

With forEach(), in this case, we'll declare the array first, and append the forEach() next. The forEach() uses a callback function to execute for each element in our array. We'll be using JavaScript's ES6 syntax with arrow functions. We used "item" as our first argument. This could take any name, we're just giving the 

<dd>prepList.forEach((item, index) => {</dd>
    <dd>let num = index + 1;</dd>
    <dd>console.log(`${num}. ${item}`);</dd>
<dd>});</dd>
