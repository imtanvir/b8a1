# Access Modifiers

- `public`: anyone can use it (default)
- `protected`: the class and its child classes
- `private`: only inside the class
- `readonly`: can't be changed after the constructor

```ts
class Account {
  private pin: string;
  protected owner = "admin";
  #balance = 0;

  constructor(public readonly id: string, pin: string) {
    this.pin = pin;
  }
}
```

Note: TS `private` is only checked while compiling. `#balance` is really private at runtime.

`public readonly id` in the constructor creates and sets the field, so you don't need `this.id = id`.