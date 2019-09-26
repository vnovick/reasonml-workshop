# Practical ReasonML for React devs

Reason lets you write simple, fast and quality type safe code while leveraging both the JavaScript & OCaml ecosystems. In this workshop we won't only see how and why we should write our code in ReasonML, but talk about practical applications of using ReasonML in new or existing React projects

## What we will cover today

- ReasonML core syntax
  - type inference
  - bindings, functions and named arguments
  - loops and conditionals
  - tuples
  - Variants
  - records and objects
  - pattern matching
  - lists and arrays
- Bucklescript
  - Setting your Javascript app with Reason
  - Writing bindings for libraries
  - Bucklescript standard lib
  - Dealing with Promises
  - Json encoding and decoding with `bs-json`
  - Fetching data with `bs-fetch`
- ReasonReact
  - Core syntax
  - State management and hooks
  - importing existing JS/TS components into Reason
- GraphQL in Reason
  - using reason-apollo and reason-apollo-hooks

# Let's get started

## Step1 setup

- Install reason cli

`yarn global add reason-cli@latest-macos`

- install [reason-vscode](https://reasonml.github.io/docs/en/editor-plugins) plugin

- Create a new project `mkdir myReasonProject`

```bash
mkdir myReasonProject
npm init
```

- Add `bs-platform`

`yarn add bs-platform --dev`

- Add `bsconfig.json`

```json
{
  "name": "reasonml-workshop",
  "reason": { "react-jsx": 3 },
  "bsc-flags": ["-bs-super-errors"],
  "sources": [
    {
      "dir": "src",
      "subdirs": true
    }
  ],
  "package-specs": [
    {
      "module": "es6",
      "in-source": true
    }
  ],
  "suffix": ".js",
  "namespace": true,
  "refmt": 3
}
```

## Excercises

### Core syntax

Run the following in `rtop` and in web console and compare results

- `false != 0 && 3 <= 4`
- `1.5 *. 1e3 /. 5`
- `12. /. 5. *. 4.`
- What replacement for the function `f` renders the expression `f("3") < 1415` correct?
- write a function that takes an integer x between 10 and 99 and returns an integer whose digits have been exchanged exchanged (73) = 37;

write a function that takes two arguments of 3 dimensional vectors and multiply them It's also called cross product and is calculated as following:

![](https://camo.githubusercontent.com/21f93b353d1cb69bf6169e89b6612dc2641e0c7c/68747470733a2f2f77696b696d656469612e6f72672f6170692f726573745f76312f6d656469612f6d6174682f72656e6465722f7376672f31653434666432336637383864326635383966323633343432343537363535313165353232653562)

- Create a sample api response record containing fields name, lastName, age, aboutMe, twitterHandle
- Create an response variant type that will return different request states. Loading, Error with error codes, response of api response type you've created earlier
- Pattern match on the api response and return different messages for different network errors, if the name in response is yours, then print custom messages

- Using [List](https://reasonml.github.io/api/List.html) sorting functions sort the following list to be unique, reverse it and convert each element to string [8,5,3,5,2,6,2,5,8,3,6,7]
