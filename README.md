# big-O-for-burritos
A set of exercises optimized for those coming from a background in burritos. Those familiar only with tortillas will want to review meat, cheese, and rice.

```C

void function foo(n) {
  int count = 0; // 1

  for(int i = 0; i < n; i++) { // 2n + 1
    count++; // 1 * n
  }
}
```

Complexity: `O(3n + 2)`
Complexity Class: `O(n)`

We have 1 operation to initialize the `count` to 0. One could
also consider the initialization of `count` to be it's own
operation, but it doesn't really matter.

The `for` loop definition intializes `i` to 0 once.

Then, `n` times, the loop checks if `i` is less than `n` and increments `i`, so
2 * `n`.

In the body of the loop, we increment count `n` times.

So, there roughly exactly just about 3`n` + 2 operations. If `n` is 1, then
there are 5 operations. If `n` is 100, there are 302 operations.
