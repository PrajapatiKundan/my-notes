# RxJS

- Asynchronous: Asynchronous means not occurring at the same time
- Evolution: Callbacks > Promises > Observables
- Best practice to add $ sign at the end of observable object

## Observables

- Sequence of data emitted asynchronously over period of time
- This data can be of any type: string, events etc
- Observable is a function that take observer as argument and provide lots of methods like create(), subscribe()
- Observable is an outer container
- Mostly used for:
  1. Http
  2. Routing
  3. Event handling

> Observable can be created with two ways:

    1. RxJs operator "of"
    2. new Observable<>() - with new keyword

## Observer

- Keep track on observable
- Continuously listening to observable
- Observer is an Object with three properties as a method: next, error, complete
- Has three methods:
  1. next()
  2. error()
  3. complete()

> Note:
>
> - Each observable contains its own observable and they are not shareable and reusable.
> - Observers cannot interact with each other

## Subject

- Subject is both observable and observer

## Subscription or Subscribe

- Observable has no use until we subscribe it
- One observable can have multiple subscribers
- We can unsubscribe observable

## RxJS Operators

Two type:

1. Pipeable operator:

- Pipeable Operators are the kind that can be piped to Observables using the syntax observableInstance.pipe(operator())
- When called, they do not change the existing Observable instance. Instead, they return a new Observable, whose subscription
  logic is based on the first Observable.
- A Pipeable Operator is a function that takes an Observable as its input and returns another Observable.
  It is a pure operation: the previous Observable stays unmodified.

- Note:
  "obs.pipe(op1(), op2(), op3(), op4());" is similar to "op4()(Op3()(op2()(op1()(obs))))

2. Creation operator:

- Creation Operators are the other kind of operator, which can be called as standalone functions to create a new Observable
- For example: of(1, 2, 3) creates an observable that will emit 1, 2, and 3, one right after another.

## Resources

[Operator Decision Tree](https://rxjs.dev/operator-decision-tree)
