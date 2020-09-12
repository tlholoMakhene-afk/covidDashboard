This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## What Is A REST API
A REST API is an API that follows what is structured in accordance with the REST Structure for APIs. REST stands for “Representational State Transfer”. It consists of various rules that developers follow when creating APIs.

## THE BENEFITS OF REST APIS
Very easy to learn and understand;
It provides developers with the ability to organize complicated applications into simple resources;
It easy for external clients to build on your REST API without any complications;
It is very easy to scale;
A REST API is not language or platform-specific, but can be consumed with any language or run on any platform.


## A Promise is an object representing the eventual completion or failure of an asynchronous operation. Since most people are consumers of already-created promises, this guide will explain consumption of returned promises before explaining how to create them.

Essentially, a promise is a returned object to which you attach callbacks, instead of passing callbacks into a function.

Imagine a function, createAudioFileAsync(), which asynchronously generates a sound file given a configuration record and two callback functions, one called if the audio file is successfully created, and the other called if an error occurs.

Here's some code that uses createAudioFileAsync():

function successCallback(result) {
  console.log("Audio file ready at URL: " + result);
}

function failureCallback(error) {
  console.error("Error generating audio file: " + error);
}

createAudioFileAsync(audioSettings, successCallback, failureCallback);
Modern functions return a promise that you can attach your callbacks to instead:

If createAudioFileAsync() were rewritten to return a promise, using it could be as simple as this:

createAudioFileAsync(audioSettings).then(successCallback, failureCallback);
That's shorthand for:

const promise = createAudioFileAsync(audioSettings); 
promise.then(successCallback, failureCallback);
We call this an asynchronous function call. This convention has several advantages. We will explore each one.

Guarantees
Unlike old-fashioned passed-in callbacks, a promise comes with some guarantees:

Callbacks will never be called before the completion of the current run of the JavaScript event loop.
Callbacks added with then(), as above, will be called even after the success or failure of the asynchronous operation.
Multiple callbacks may be added by calling then() several times. Each callback is executed one after another, in the order in which they were inserted.
One of the great things about using promises is chaining.