# React-Native-Stack-Snap-Carousel

# Introduction

In this, we will discuss how to integrate Carousel in a React Native application.
Carousels are widely used by many big websites, such as Amazon, Flipkart, etc. The same design element has been ported to mobile apps like Tinder, which uses swipe animation.

# Demo 
![stack_](https://user-images.githubusercontent.com/86215353/181409527-2cd6b95f-e6e1-4daf-903c-f97b220b2c38.gif)


# Installation
```
npm i react-native-snap-carousel
```

# Example
```js
import React, {useState, useRef} from 'react';
import {Text, View, Dimensions, Image} from 'react-native';
import Carousel, {Pagination} from 'react-native-snap-carousel';

export const SLIDER_WIDTH = Dimensions.get('window').width + 30;
export const ITEM_WIDTH = Math.round(SLIDER_WIDTH * 0.8);

const data = [
  {
    id: 1,
    name: 'Meeting',
    url: 'https://images.unsplash.com/photo-1624555130581-1d9cca783bc0?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2071&q=80',
  },
  {
    id: 2,
    name: 'Teacher',
    url: 'https://images.unsplash.com/photo-1587691592099-24045742c181?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NXx8dXJsfGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=500&q=60',
  },
  {
    id: 3,
    name: 'Phone',
    url: 'https://images.unsplash.com/photo-1517404215738-15263e9f9178?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Nnx8dXJsfGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=500&q=60',
  },
];

const renderItem = ({item}) => {
  return (
    <View
      style={{
        borderWidth: 1,
        padding: 20,
        borderRadius: 20,
        alignItems: 'center',
        backgroundColor: 'white',
      }}>
      <Image source={{uri: item.url}} style={{width: 300, height: 200}} />
      <Text style={{marginVertical: 10, fontSize: 20, fontWeight: 'bold'}}>
        {item.name}
      </Text>
    </View>
  );
};

const App = () => {
  const [index, setIndex] = useState(0);
  const isCarousel = useRef(null);
  return (
    <View style={{paddingTop: 200,
      alignItems: 'center',
      flex: 1}}>
      <Carousel
      layout={'stack'} layoutCardOffset={`18`}
        ref={isCarousel}
        data={data}
        renderItem={renderItem}
        sliderWidth={SLIDER_WIDTH}
        itemWidth={ITEM_WIDTH}
        onSnapToItem={index => setIndex(index)}
      />
    </View>
  );
};

export default App;

```

# Tutorial

Coming Soon...
