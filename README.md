# Unable to move pure-rand to yarn 3+

**Context:**

We try to move `pure-rand` to Yarn 2+. Move has been done several months ago for `fast-check` itself but so far I have not spent the time to move this library while the benefit is definity **huge**.

**What happens?**

- `pure-rand` is a seeded number generator library
- `pure-rand` uses `fast-check`, a property based testing library, to test itself
- `fast-check` is using `pure-rand` internally to generate random values

With Yarn 3+, when I try to install the dependencies, Yarn just ignores `pure-rand` pulled by `fast-check`:

- it does not pull anything from npm repository
- nor create a simlink to the instance of `pure-rand` defined in the repo
