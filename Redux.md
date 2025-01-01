## What is The Redux ?
*Redux is simply a store to store the state of the variables in your app. Redux creates a process and procedures to interact with the store so that components will not just update or read the store randomly. Similar to the bank. It does not mean because you have money in the bank that you can go anytime, open the vault, and take money. You have to go through certain steps to withdrawal money.
In short, Redux is a way to manage the “state” or we can say it is a cache or storage that can be accessed by all components with a structured way. It has to be accessed through a “Reducer” and “Actions”*
![1_GQWc13FLOcb7SXQ2nQsMtA](https://github.com/user-attachments/assets/44e72ddc-4c3a-4b9f-af3b-facb7f065034)

* * *
## Redux vs Context ?
 **Context and Redux are very different tools that solve different problems, with some overlap.**

Context is not a "state management" tool. It's a Dependency Injection mechanism, whose only purpose is to make a single value accessible to a nested tree of React components. It's up to you to decide what that value is, and how it's created. Typically, that's done using data from React component state, ie, useState and useReducer. So, you're actually doing all the "state management" yourself - Context just gives you a way to pass it down the tree.

Redux is a library and a pattern for separating your state update logic from the rest of your app, and making it easy to trace when/where/why/how your state has changed. It also gives your whole app the ability to access any piece of state in any component.

In addition, there are some distinct differences between how Context and (React-)Redux pass along updates. Context has some major perf limitations - in particular, any component that consumes a context will be forced to re-render, even if it only cares about part of the context value.

Context is a great tool by itself, and I use it frequently in my own apps. But, Context doesn't "replace Redux". Sure, you can use both of them to pass data down, but they're not the same thing. It's like asking "Can I replace a hammer with a screwdriver?". No, they're different tools, and you use them to solve different problems. 

* * *
## How React and Redux work with each other:
**The react-redux library provides 2 components: provider & connect components.**

**First** we wrap the component which needs some data from the store with connect component which is connected to the provider, the provider takes the data from the store and give it to the connect component which in turn passes it to the component that needs data from store, by this way we pass data from store to a component which is not a direct child to the App component.

Provider:

The `<Provider/>` makes the Redux store available to any nested components that have been wrapped in the connect() function.

Since any React component in a React-Redux app can be connected, most applications will render a `<Provider/>` at the top level, with the entire app’s component tree inside of it.

Connect:

The connect() function connects a React component to a Redux store.

It provides its connected component with the pieces of the data it needs from the store, and the functions it can use to dispatch actions to the store.

connect accepts four different parameters, all optional(we can put null instead of anyone we don `t want to use). By convention, they are called:

**mapStateToProps:** any time the store is updated, mapStateToProps will be called. The results of mapStateToProps must be a plain object, which will be merged into the wrapped component’s props. If you don’t want to subscribe to store updates, pass null or undefined in place of mapStateToProps.
    -mapStateToProps function takes 2 parameters (state,ownProps), if we put both parameters mapStateToProps will be called whenever the store state changes or when the wrapper component receives new props.

**mapDispatchToProps:** may either be an object, a function
-If this parameter is null, Your component will receive dispatch by default
-mapDispatchToProps takes 2 parameters (dispatch,ownProps)
will be called with dispatch as the first parameter and the props passed to the wrapper component as the second parameter and will be re-invoked whenever the connected component receives new props.
-mapDispatchToProps functions are expected to return an object. Each field of the object should be a function, calling which is expected to dispatch an action to the store.
-The return of your mapDispatchToProps functions is regarded as dispatchProps. It will be merged as props to your connected component. If you define mergeProps, it will be supplied as the second parameter to mergeProps.

* * *
## To use React-Redux:
1) `npm install — save react-redux`
2) import provider from react-redux.
3) wrap the App component by the provider tag and pass the store as a prop to it.



![code2](https://github.com/user-attachments/assets/478ea5c5-4bb5-4577-8c53-0b37d1453246)




4) import connect from react-redux.
5) use the connect in the component and pass inside it the action creator or/and a mapStateToProps function which takes state (all data inside the store) as a parameter and turns the state to props which we can access anywhere inside our component.





![code.png](:/0753b![code3](https://github.com/user-attachments/assets/b3fcb1c7-cdf6-4cd1-b582-c9fd4e4b48b9)

## Implement useSelector/useDispatch:
We import the following hooks from react-redux, useSelector and useDispatch. Before, we had to import connect() from react-redux and wrap our components with it in order to map state to props and map dispatch to props.

**useSelector**
The equivalent of map state to props is useSelector. It takes in a function argument that returns the part of the state that you want. In this case, we have the following keys from state defined, counter and currentUser. We defined these earlier when combining reducers.

**useDispatch**
The equivalent of map dispatch to props is useDispatch. We will invoke useDispatch and store it to a variable, dispatch. Dispatch will work with the allActions imported from the actions folder. For example, useEffect calls a dispatch with the following action, allActions.userActions.setUser(user). User is defined as:

![code](https://github.com/user-attachments/assets/6ea6321f-4556-4939-9608-68c73a94e362)

* * *




**Thank You..**
