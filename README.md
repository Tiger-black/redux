# redux
 学习redux
一、预备知识
	阅读本文，你只需要懂 React。如果还懂 Flux，就更好了，会比较容易理解一些概念，但不是必需的。
	Redux 有很好的文档，还有配套的小视频（前30集，后30集）。你可以先阅读本文，再去官方材料详细研究。
	我的目标是，提供一个简洁易懂的、全面的入门级参考文档。
二、设计思想
Redux 的设计思想很简单，就两句话。
	1、Web 应用是一个状态机，视图与状态是一一对应的。
	2、所有的状态，保存在一个对象里面。
	请务必记住这两句话，下面就是详细解释。
三、基本概念和 API
	3.1 Store
	Store 就是保存数据的地方，你可以把它看成一个容器。整个应用只能有一个 Store。
	Redux 提供 createStore 这个函数，用来生成 Store。

	import { createStore } from 'redux';
	const store = createStore(fn);
	上面代码中， createStore 函数接受另一个函数作为参数，返回新生成的 Store 对象。

3.2 State
	Store对象包含所有数据。如果想得到某个时点的数据，就要对 Store 生成快照。这种时点的数据集合，就叫做 State。
	当前时刻的 State，可以通过store.getState()拿到。

	import { createStore } from 'redux';
	const store = createStore(fn);

	const state = store.getState();
	Redux 规定， 一个 State 对应一个 View。只要 State 相同，View 就相同。你知道 State，就知道 View 是什么样，反之亦然。

3.3 Action
	State 的变化，会导致 View 的变化。但是，用户接触不到 State，只能接触到 View。所以，State 的变化必须是 View 导致的。
	Action 就是 View 发出的通知，表示 State 应该要发生变化了。
	Action 是一个对象。其中的type属性是必须的，表示 Action 的名称。其他属性可以自由设置，社区有一个规范可以参考。

	const action = {
	  type: 'ADD_TODO',
	  payload: 'Learn Redux'
	};
	上面代码中，Action 的名称是ADD_TODO，它携带的信息是字符串Learn Redux。
	可以这样理解，Action 描述当前发生的事情。改变 State 的唯一办法，就是使用 Action。它会运送数据到 Store。

3.3 Action
	State 的变化，会导致 View 的变化。但是，用户接触不到 State，只能接触到 View。所以，State 的变化必须是 View 导致的。Action 就是 View 发出的通知，表示 State 应该要发生变化了。
	Action 是一个对象。其中的type属性是必须的，表示 Action 的名称。其他属性可以自由设置，社区有一个规范可以参考。

	const action = {
	  type: 'ADD_TODO',
	  payload: 'Learn Redux'
	};
	上面代码中，Action 的名称是ADD_TODO，它携带的信息是字符串Learn Redux。
	可以这样理解，Action 描述当前发生的事情。改变 State 的唯一办法，就是使用 Action。它会运送数据到 Store。














































