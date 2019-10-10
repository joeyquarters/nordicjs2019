# Mind Reading With Intelligent & Adaptive UI's

by David Khourshid ([@DavidKPiano](https://twitter.com/davidkpiano))

## A/B tests are ineffective

User flows are seldom linear. One size **doesn't** fit all.

[Guess.js](https://github.com/guess-js/guess) — tool to predict which page a user will likely go to next using Google Analytics

## Adaptive User Interfaces

Adapt to the **user**, not to the _device_ (which would be a responsive user interface). Examples: Cortana, Google Home.

Provides a mapping of where users can go and what they can do in an application.

Provides super users quicker flows and newbie users a more helpful flow.

## Model-drive development

A solution for building complex adaptive user interfaces. More formally, this is known as a **Finite State Machine**.

- have one initial state
- a finite number of states
- a mapping of state transitions, triggered by user interaction
- a finite number of final states

### Building a FSM

- `switch`/`case` statements
- object mapping
- [Xstate](https://github.com/davidkpiano/xstate)

### What we need

- Weighted graphs for user actions
- Decision trees
- Prediction via shortest paths

### Example

A component sends user path data to analytics. There are many paths to get to the end state, and we use those analytics to determine the quickest path. The component then uses this data to predict what path to send the user down.

## Modeling Considerations

### Micro vs. macro adaptivity

Do we adapt at the component or app level?

### Prediction vs. feedback

Users may want more control than what you provide in an adaptive interface

## Resources

- [The World of Statecharts](statecharts.github.io)
