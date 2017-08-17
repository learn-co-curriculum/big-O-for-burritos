<iframe id="typeform-full" width="80%" height="80%" frameborder="0" src="https://theflatironschool.typeform.com/to/I9TsNU"></iframe>




# big-O-for-burritos

A set of exercises optimized for those coming from a background in burritos. Those familiar only with tortillas will want to review meat, cheese, and rice.

## Instructions

Complete each exercise. "order" refers to the general Big O order, like
O(1), O(n), or O(n log(n)). "complexity" refers to a more specific
approximation of computations necessary, like `13n + 42` or `12`.

## Example

```C

void foo(n) {
  int count = 0; // 1

  for(int i = 0; i < n; i++) { // 2n + 1
    count++; // 1 * n
  }
}
```

Complexity: `3n + 2` Order: `O(n)`

We have 1 operation to initialize the `count` to 0. One could
also consider the initialization of `count` to be it's own
operation, but it doesn't really matter.

The `for` loop definition intializes `i` to 0 once.

Then, `n` times, the loop checks if `i` is less than `n` and increments `i`, so
2 * `n`.

In the body of the loop, we increment count `n` times.

So, there roughly exactly just about 3`n` + 2 operations. If `n` is 1, then
there are 5 operations. If `n` is 100, there are 302 operations.

## Exercise 1

Calculate the complexity and order.

Try writing the complexity next to each line like in the example as a
tool to calculating the complexity.

```C
int rectangle_area(height, width) {
  int area = 0;

  for(int i = 0; i < height; i++) {
    for(int j = 0; j < width; j++) {
      area++;
    }
  }

  return area;
}
```

Complexity: _______________ Order: _______________

## Exercise 2

Calculate the order.

*ONLY CALCULATE THE ORDER, YES THERE IS A TRICK*

```C
int cheese_shredder(float height_of_cheese_wheel) {
  float dist_to_moon_km = 370300;
  float stacked_cheese_height_km = 0;
  int num_cheese_shredders = 5;
  int num_technicians_per_shredder = 2;
  int shred_time = 12;
  int total_shred_time = 0;

  while(stacked_cheese_height_km < dist_to_moon_km) {
    stacked_cheese_height_km = stacked_cheese_height_km + height_of_cheese_wheel;
  }

  for(int i = 0; i < num_cheese_shredders; i++) {
    // Proprietary cheese calculation heuristic
    for(int j = 12; j < 123456; j = j + 6) {
      for(int k = 21; k < 123456; k = k + 6) {
        total_shred_time  = total_shred_time + stacked_cheese_height_km / (stacked_cheese_height_km - 2.0);
      }
    }
  }

  return total_shred_time;
}
```

Order: _______________

## Exercise 3

Calculate the complexity and order.

```C
int halves(n) {
  int count = 0;

  if(n % 2 == 1) {
    n = n - 1;
  }

  for(int i = n; i > 1; i = i / 2;) {
    count++;
  }

  return count;
}
```

Complexity: _______________ Order: _______________


## Exercise 4

Calculate the complexity and order.

```C
int bacteria_generation(days) {
  int total_population = 1;
  int current_population = total_population;

  for(int i = 0; i < days; i++) {
    current_population = total_population;

    for(int j = 0; j < current_population; j++) {
      total_population++;
    }
  }

  return total_population;
}
```

Complexity: _______________ Order: _______________

## Exercise 5

Which algorithm is more efficient? (burrito is not a valid answer)

Algorithm A

```C
int max(array) {
  int max = array[0];

  for(int i = 1; i < array.length; i++) {
    if(array[i] > max) {
      max = array[i];
    }
  }

  return max;
}
```

Algorithm B

```C
int max(array) {
  int temp;

  // sort the array in ascending order
  for(int i = 0; i < array.length; i++) {
    for(int j = 0; j < array.length - 1; j++) {
      if( array[j] > array[j+1]) {
        temp = array[j+1];
        array[j+1] = array[j];
        array[j] = temp;
      }
    }
  }

  return array[array.length-1];
}
```

Algorithm A

Order: _______________

Algorithm B

Order: _______________

Winner: _______________

## Exercise 6

Which algorithm, foo or bar, is faster when when `n` is 10? 100? 1000?

Algorithm foo

```C
  int foo(n) {
    int sum = 0

    for(int i = 0; i < n + 500; i++) {
      sum++;
    }

    return sum;
  }
```

Algorithm bar

```C
  int bar(n) {
    int sum = 0

    for(int i = 0; i < n; i++) {
      for(int j = 0; j < n; j++) {
        sum++;
      }
    }

    return sum;
  }
```

### n=10

foo complexity: __________ bar complexity: __________ winner: __________

### n=50

foo complexity: __________ bar complexity: __________ winner: __________

### n=1000

foo complexity: __________ bar complexity: __________ winner: __________

### n=1000

foo complexity: __________ bar complexity: __________ winner: __________
