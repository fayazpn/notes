# Next.js route handlers

Map: [[Maps/Web development|Web development]]

## Summary

A Route Handler exposes an HTTP endpoint by exporting method handlers from a `route.ts` file.

## Key points

- Export methods such as `GET` or `POST` from the route's file under `app/`.
- The request uses the Web Request API; body parsing such as `request.json()` is asynchronous.
- Return a Response or supported Next.js response wrapper with an appropriate status and headers.
- Hosting determines whether the handler runs in a long-lived server or a managed function environment; the file convention alone does not guarantee a particular deployment lifecycle.

## Example

```ts
export async function POST(request: Request) {
  const input = await request.json();
  return Response.json({ received: input }, { status: 201 });
}
```

## Related

- [[Notes/Systems/REST API design|REST API design]]
- [[Notes/Systems/CORS|CORS]]
- [[Notes/Web/Next.js routing and structure|Next.js routing and structure]]
