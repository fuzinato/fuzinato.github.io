---
layout: post
title: React's Context API
date: 2018-03-14 00:00:00 +0000
category: React
tags: react
resources: http://wesbos.com/react-context/
---
Passing props to deeply nested components in react has been challenging, especially if the app is small and it does not justify having dedicated state management (redux). But as of react 16.3, there is a Context API that helps pass props to children without "props drilling".
First we need a _context_ `const MyContext = React.createContext()` and create a _provider_ component where state is going to live:
```
class MyProvider extends React.Component {
  state = {
  	name: 'Dario'
  }
  render() {
    return (
      <MyContext.Provider value={this.state.name}>
        {this.props.children}
      </MyContext.Provider>
    )
  }
}
```
Now we can wrap our app or parent component inside _MyProvider_ cpomponent and evety child regardless how deeply nested cound retrieve value that was passed in MyProvider component