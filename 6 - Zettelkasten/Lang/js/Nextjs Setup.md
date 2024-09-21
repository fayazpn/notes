
- nvmrc - 18.17.0
- .npmrc - engine-strict=true
- package.json
```json
"engines": {
    "node": ">=18.17.0",
    "yarn": "please-use-npm",
    "pnpm": "please-use-npm"
  },
```

- eslint
```json
{
  "extends": ["next", "next/core-web-vitals", "eslint:recommended"],
  "globals": {
    "React": "readonly"
  },
  "rules": {
    "no-unused-vars": "warn"
  }
}
```

- .prettierrc - `npm i prettier -D`
```json
{
  "tabWidth": 2,
  "semi": true,
  "singleQuote": true,
  importOrder: [

"^(react/(.*)$)|^(react$)",

"^(next/(.*)$)|^(next$)",

"<THIRD_PARTY_MODULES>",

"",

"^types$",

"^@/env(.*)$",

"^@/types/(.*)$",

"^@/config/(.*)$",

"^@/lib/(.*)$",

"^@/hooks/(.*)$",

"^@/components/ui/(.*)$",

"^@/components/(.*)$",

"^@/styles/(.*)$",

"^@/app/(.*)$",

"",

"^[./]",

],
}
```

.prettierignore

```
dist
node_modules
package.json
```

.env.example



***

```
src/
├── app/
│   └── (routes)
├── components/
│   ├── ui/             # shadcn components
│   └── advanced/         # your custom components
|	    └── ComponentName/  
|	        ├── ComponentName.tsx 
|	        ├── ComponentName.types.ts
├── lib/
│   └── utils.ts        # utility functions
├── hooks/
│   └── useMyHook.ts  
├── config/
│   └── dashboard.ts  
├── server/
│   └── queries.ts # api utility functions 
├── styles/
│   └── globals.css     # global styles including Tailwind
├── types/              # TypeScript type definitions
│   ├── api/ # API-related types
│   │   ├── requests/ 
│   │   ├── responses/ 
│   │   └── index.ts 
│   ├── common.ts # shared types across the application
├── tests/
│   └── __mocks__/
└── stories/            # Storybook stories

public/
.storybook/
jest.config.js
tailwind.config.js
tsconfig.json
```


```ts
export interface ApiResponse<T> { data: T; message: string; } // File: lib/api.ts 
const API_BASE_URL = process.env.API_BASE_URL; // This should be your FastAPI backend URL 
export async function fetchFromAPI<T>( 
endpoint: string, options: RequestInit = {} ): Promise<T> { 
	const url = `${API_BASE_URL}${endpoint}`; 
	const response = await fetch(url, { ...options, 
	headers: { 'Content-Type': 'application/json', 
	...options.headers, 
	}, 
	}); 
	if (!response.ok) { 
		throw new Error(`API request failed: ${response.statusText}`); 
	} 
	return response.json(); 
}


const data = await fetchFromAPI<ApiResponse<User>>('/users', { method: 'POST', body: JSON.stringify(userData), });


const response = await fetch(`${process.env.BASE_URL}/api/users`, { method: 'POST', headers: { 'Content-Type': 'application/json' }, body: JSON.stringify(userData), });


const response = await fetch('/api/users', { method: 'POST', headers: { 'Content-Type': 'application/json' }, body: JSON.stringify(userData), });

```



**Todo**

- .d.ts file