# fogulang_module

A small [Fogu](https://github.com/microaitec-deploy/fogulang) library published on
GitHub. It exists to verify that Fogu installs packages from a git URL.

```sh
fogu add microaitec-deploy/fogulang_module      # or github:microaitec-deploy/fogulang_module
```

```fogu
import mod from "fogulang_module"
import { Counter } from "fogulang_module"

print(mod.greet("Ana"))              // Hello, Ana!
print(mod.greet("Ana", "pt"))        // Olá, Ana!
print(mod.slug("Hello World Fogu"))  // hello-world-fogu
print(mod.sum([1, 2, 3]))            // 6

const c = new Counter(5)
print(c.next(), c.next())            // 5 10
```

| Export | What it does |
| --- | --- |
| `version` | the library version |
| `greet(name, lang = "en")` | a greeting in English or Portuguese (`"pt"`) |
| `slug(text)` | lower-case words joined with `-` |
| `sum(xs)` | the sum of a list of numbers |
| `Counter` | `new Counter(step = 1)`; `next()` adds the step and returns the value; `reset()` |

Tests: `fogu test` (runs `main.test.fg`). MIT.
