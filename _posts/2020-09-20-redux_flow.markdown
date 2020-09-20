---
layout: post
title:      "Redux Flow"
date:       2020-09-20 17:22:41 +0000
permalink:  redux_flow
---


Action

Reducer

State

How does it all work?

All through functions.

That is how Javascript gets anything done, with the use of functions.

### FLOW

What I will be talking to you here is the redux flow.

From the Action to the Reducer to State being updating.

### ACTION

You have your actions which are called upon with a dispatch. They get dispatched from the container to it’s child components. A good practice would be to have these actions passed to presentational components or stateless functional components. You can pass it down as props to the function in question.

In order for actions to be dispatched we would have to also import `connect` from ‘react-redux’ in order for those actions to be called upon and run through the reducer. In order for one to pass that function/action to a child component we would also have to map out those functions in a map Dispatch to the props function, mapDispatchToProps. Inside of that function we pass in dispatch as an argument and that dispatch is what helps to call upon that action.

You usually have a the container component holding all the logic and storing the data. In it’s child or children components you would then pass in the values and have them display the data themselves. One could even argue that it would be most beneficial to have multiple SFC’s(stateless functional components).

One could have a form that only holds/contains another function that holds just inputs. Or if you are mapping data you can even have a component that has <ul></ul> tags and inside of those tags render another component that has that data being mapped out. What you could do as well would be to pass the props from the parent container to the child container as well.

```
import React from 'react';
import RandomComponentChild from '../stateless/RandomComponentChild';
const RandomComponent = (props) => {
return (
<div>
<ul>
<RandomComponentChild props={props} />
</ul>
</div>
)
}
export default RandomComponent
```


Only possible because of REDUX

```
import React from 'react';
import RandomComponentChild from '../stateless/RandomComponentChild';
const RandomComponent = (props) => {
return (
<div>
<ul>
<RandomComponentChild props={props} />
</ul>
</div>
)
}
export default RandomComponent
```

####*REDUCER*
The reducer does it what one would think. reduce the data it was given to a single value. taking an array and saving it to an object.

The reducer is also a function, but it is called a pure function. The reason being is that it doesn’t destructively destroy or update the state. What it does is takes in an argument of state and action with a payload. Depending on what the action is it will do that `something` to the state, the copy of state. To do so there are a few ways to go about that. You can either use Object.assign or you can use the spread operator {…state} which is just a copy of the whole state.

####*STATE*
The state gets updating when it goes through the reducer.

The action gets dispatched by the dispatch function then it goes to the reducer usually with a switch statement. Then a copy of the state is made and depending on the action that copy may be reduced to single value, a reduced to an object, or just one thing/object may be displayed. Then to render that thing to other components you would then need to map over the state pass it as props to other components
