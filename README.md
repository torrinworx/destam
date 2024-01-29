# Destam - Delta State Manager

A state management library that doesn't consider mutation as taboo and generalizes mutation events through deltas.

```js
const state = OObject({
	name: 'John Doe',
	address: 'Tokyo',
});

state.observer.path('address').watch(delta => {
	console.log(`${delta.getParent().name}'s address changed to ${delta.value}`);
});

state.address = 'Toronto';
```

Destam is a library that provides no nonsense state containers that act just like ordinary javascript Arrays or Objects through a proxy interface. These state containers can then simplify all state changes down to an optimal series of deltas that can later be undone or replayed.

Deltas can be used to optimally:
 - Update the DOM to synchronize with the application's state
 - Send over the wire to synchrorize with other computers
 - Implement realtime collaboration
 - Update the Database

See [an introduciton](destam/docs/intro.md)

Documentation is split across multi-line comments in the source code for documentation about specific functions and functionality and the markdown files are for high level ideas. It's recommended to read everything under ./docs before starting an application with Destam.
