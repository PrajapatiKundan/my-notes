# Angular learning

## Lazy loading

**Step - 1**

Run following command to create feature module:

```sh
ng g m new-item --routing
```

This will create `new-item.module.ts` and `new-item-routing.module.ts` files in `/new-item` folder

**Step - 2**

Run following command to add component in feature module

```sh
ng g c new-item/my-component --module new-item
```

This will create `my-component` component in `/new-item` folder and register it in `new-item.module.ts` file.

**Step - 3**

Add following code to the **Routes** array `app-routing.module.ts` file

```typescript
{
  path: 'add',
  loadChildren: () => import('./new-item/new-item.module').then((m) => m.NewItemModule),
},
```

This will load new-item module when route is `/add`

> Note:<br>
> Notice that the lazy-loading syntax uses loadChildren followed by a function that uses the browser's built-in import('...') syntax for dynamic imports. The import path is the relative path to the module.<br><br> > _forRoot()_ - It specify that this is root routing module. It is used only once in application. This method tells Angular to instantiate an instance of the Router class under the hood, and there can be only one router in your app<br><br> > _forChild()_ - This static method tells angular that there is already a Router instance available in the app so please just register all of these routes with that instance.
