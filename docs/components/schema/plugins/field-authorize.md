The authorize plugin allows us to define field-level authorization to a query.

```ts
t.field('postById', {
  type: Post,
  args: { id: idArg() },
  authorize: (root, args, ctx) => ctx.auth.canViewPost(args.id),
  resolve(root, args, ctx) {
    return ctx.post.byId(args.id)
  },
})
```
