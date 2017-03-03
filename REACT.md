React (and Redux and javascript and other stuff)
========

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

If you iterate over children in parent `render()` function then you can mess with props of children w/o breaking immutablility b/c children won't be rendered yet

Most of this [learned from here](https://jaketrent.com/post/send-props-to-children-react/)