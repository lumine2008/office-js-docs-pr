---
ms.date: 1/30/2019
description: Discover a pattern for batching API calls when using custom functions in Excel.
title: Batching Web Requests with Custom Functions
localization_priority: Priority
---

# Batching API calls pattern


# Batching web requests

Custom functions allow you to make requests to resources on the web and this article will detail a pattern to batch these requests. When batching, you'll bundle individual requests together into a larger request, rather than executing each request one by one.

> [!NOTE]
> This article assumes you're familiar with JavaScript Promises and assumes you've created a custom function before. To learn how to create a custom function, see the [Custom functions tutorial](../tutorials/excel-tutorial-create-custom-functions.md).

## Clone the batching code sample repository

This article is explained with a code sample, available in [this Github repository](https://github.com/OfficeDev/PnP-OfficeAddins/tree/master/Excel-custom-functions). Complete the following steps to get started with the code sample:

1. Clone the repository to your local computer and open the repository’s root folder. You'll notice there are two files:

    * The file named fill-in.js is a set of code which you will fill in, given instructions in this tutorial.
    * The file named final-batching-sample.js gives a full code sample if you prefer to look at a whole code sample right away.

2. Open the file named fill-in.js in your favorite code editor.

3. Follow the steps in the next section to fill in the code at each point you come across a `TODO` in the code sample.

## Complete the `TODO` sections of the code sample

* **TODO #1**
   In the first `TODO` section you'll create two custom functions. One is called sum, which will take two numbers and add them together. The other is called multiply, which multiplies two numbers.

    To simplify your code, you'll create a method which takes the name of the operation the function performs and its arguments, called `_pushOperation`. You'll note that many of the functions in this sample use of an underscore in front of the function name, indicating that the function is not publicly accessible.

    Fill in the functions according to the following:

    ```JavaScript
    function sum() {
      return _pushOperation(
        "sum",
        // The last argument is an InvocationContext. Skip it.
        Array.from(arguments).slice(0, -1));
    }

    function mul() {
      return _pushOperation(
        "mul",
        // The last argument is an InvocationContext. Skip it.
        Array.from(arguments).slice(0, -1));
    }
    ```

## See also

* [Create custom functions in Excel](custom-functions-overview.md)
* [Custom functions metadata](custom-functions-json.md)
* [Runtime for Excel custom functions](custom-functions-runtime.md)
* [Custom functions changelog](custom-functions-changelog.md)
* [Excel custom functions tutorial](../tutorials/excel-tutorial-create-custom-functions.md)