# Next.js layouts and boundaries

Map: [[Maps/Web development|Web development]]

## Summary

Layouts share UI across route segments. Templates and boundary files control remounting, loading, and error presentation.

## Key points

- A layout is shared across navigation and can preserve client state; “renders exactly once” is not a general rendering guarantee.
- A template creates a new instance for its children on relevant navigation, resetting their state and rerunning effects.
- `loading.tsx` supplies a loading UI through a Suspense boundary. It is not inherently a Client Component.
- `error.tsx` defines a client error boundary for its segment; its scope does not mean it catches every error in the application.

## Related

- [[Notes/Web/Next.js routing and structure|Next.js routing and structure]]
- [[Notes/Web/Server and Client Components|Server and Client Components]]
