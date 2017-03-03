React (and Redux and javascript and other stuff)
========

### NOTE: written as I'm learning this stuff, so some of this could be wrong, [feel free to fix it](pulls).

## Iterate over children
children of component be like
```js
<MyComponent tag="theBestTag">
    <MyChild />
    <MyChild />
</MyComponent>
```

Children can be 1 item or an array, to abstract that away React provides `React.Children`.
```js
// do something with children, whether there is just 1 or many
React.Children.map(props.children, child =>
{
    if(child.type === MyChild){
        // do something
    }
});
```

If you iterate over children in parent `render()` function then you can mess with props of children w/o breaking immutablility b/c children won't be rendered yet (they will actually be ["descriptors"](https://facebook.github.io/react/blog/2014/07/17/react-v0.11.html#descriptors) at that point).

If you want to clone a component

Most of this [learned from here](https://jaketrent.com/post/send-props-to-children-react/)