---
layout: post
title:  "Redux Insight"
date:   2019-05-03 14:10:00 +1000
categories: Geek
---

Core Concepts
==============

##### Actions

Actions are used to tell Redux that something in an application has changed, or that the user has interacted with the application in some way. Actions in Redux are plain objects with a `type` property.

##### Reducers

In Redux, reducers are used to facilitate state transformations based on actions. It use current state and action object to compute a new state.

##### Store

The store in Redux is what coordinates passing actions to your reducer, notifying you of changes to your state. It encapsulates the state and offers an interfaace that you can use to interact with it. This interface is comprised of the following:
- dispatch(action)
- getState()
- subscribe(listener)

##### Middleware

Middleware acts as a pipeline that all dispatched actions go through before reaching the store. And actually middleware in Redux provide a interface to make a plugin-system possible.

##### Selector
Selectors are functions that accept a state from the Redux store and compute data that will eventually be passed as props to React. 

Redux Saga
========================
Redux Saga is a library to help to handle the side effect of redux -- AJAX call. It help us to think about the asynchrous code in a synchrous fashion. And because it doesn't perform the side-effect but return the descriptions of how to handle, it is very easy to test.

##### take, takeevery, takelatest
{% highlight javascript%}
// We could create channel to differentiate a series of same actions, and revisite that later.

import { channel, delay } from 'redux-saga';                           
import { call, put, take, takeLatest } from 'redux-saga/effects';      
...
export default function* rootSaga() {
   yield takeLatest('FETCH_TASKS_STARTED', fetchTasks);
   yield takeLatestById('TIMER_STARTED', handleProgressTimer);         
}

function* takeLatestById(actionType, saga) {
   const channelsMap = {};                                             

   while (true) {
      const action = yield take(actionType);
      const { taskId } = action.payload;

      if (!channelsMap[taskId]) {
         channelsMap[taskId] = channel();                              
         yield takeLatest(channelsMap[taskId], saga);                  
      }

      yield put(channelsMap[taskId], action);                          
   }
}
{% endhighlight %}

##### fork, spawn

##### put, call



###### Reference and credit:

*Developing a Redux Edge* - by Johannes Lumpe; Karl Purkhardt; Darío Cravero; Troy Mott; Art Muller; Ezekiel Chentnik - Published by Bleeding Edge Edge Press, 2016

*Redux in Action* - by Marc Garreau and Will Faurot, Published by Manning Publications, 2018
