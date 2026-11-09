# Generics and Promise

Generics let one function work with any type and still keep type safety.

- `any` turns off the type check
- `unknown` makes you check the type every time
- generic `T` = whatever type goes in, the same type comes out

```ts
function box<T>(value: T) {
  return { data: value };
}

box("hi");  // { data: string }
box(5);     // { data: number }
```

## Promise

`Promise<T>`: T is the type of the result when the promise finishes.

`res.json()` gives `any`, so typos are not caught. Pass the type yourself:

```ts
async function request<T>(url: string): Promise<T> {
  const res = await fetch(url);
  return res.json();
};

const user = await request<User>("/api/user");
```

Note: this is just a cast. The server can still send something else.