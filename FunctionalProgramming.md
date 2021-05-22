We can not process the stream twice.
This code are gonna give an error

```
Stream<Person> peopleStream = people.stream();
Stream<String> integerStream = peopleStream.map(p -> p.getName());
Stream<String> isEmpty = integerStream.filter(n -> n.isEmpty());
Stream<String> isNotEmptyStream = integerStream.filter(n -> !n.isEmpty());
long count = isEmpty.count();
long count1 = isNotEmptyStream.count();
System.out.println(count);
System.out.println(count1);
```

## Five patterns to create streams
- From a collection
- from an array
- from a text file
- from a regular expression
- from a string

From array
```
long count = Stream.of(arr).count();
System.out.println(count);

long count1 = Arrays.stream(arr).count();
System.out.println(count1);
```

```
//chars method return IntStream which is a special Stream type, then 
//we want to return it to Stream<String>
        String sentence = "the quick brown fox jumps over the lazy dog";
        IntStream chars = sentence.chars();
        Stream<String> stringStream = chars.mapToObj(c -> Character.toString(c));
        long count2 = stringStream.distinct().sorted().count();
```        

## Average, Min, Max Operations
These methods are not exist in Stream interface, only available for NumberStream
not work for Stream<T>. 
<br>
Map funtions returns Stream of T
```
<R> Stream<R> map(Function<? super T, ? extends R> mapper);
```
We need to use a map function that returns IntStream:
```
IntStream mapToInt(ToIntFunction<? super T> mapper);
```

We have three number stream classses in Java. IntStream, LongStream, and DoubleStream.
<br>
So, also three map method for these classses. So, min, max, sum, average method 
returns Optional (Int, Long, double) which is a wrapper for these types.

```
 OptionalDouble average = people.stream()
                .mapToInt(Person::getAge)
                .filter(age -> age > 20)
                .average();
```
We can simply use orElseThrow(), ifPresent() etc.

## Reduction
A reduction operator takes BinaryOperator.
<br>
A reduction operator with no identity element return an Optional.
<br>
The ideo of identit element comes from the problem when empty stream exist.
That's why this methods return Optional

```
List<Integer> integers = List.of(1, 1, 1, 1, 1);
Optional<Integer> reduce = integers.stream().reduce((i1, i2) -> i1 + i2);
```

If we provide an identity element for empty stream, the result will be 0 in this case.
```
List<Integer> of = List.of();
int reduce1 = of.stream().reduce(0, (i1, i2) -> i1 + i2);
System.out.println(reduce1);
```

If we provide an identity element for empty stream, the result will be 10 in this case.
```
List<Integer> of = List.of();
int reduce1 = of.stream().reduce(10, (i1, i2) -> i1 + i2);
System.out.println(reduce1);
```

The true version of sum is like this. Sum will be 2
```
List<Integer> of = List.of(2);
int reduce1 = of.stream().reduce(0, (i1, i2) -> i1 + i2);
System.out.println(reduce1);
```

So, in general we need to define a proper identity element.

## Collectors
```
 String collect = cities.stream()
                .filter(c -> c.length() == 5)
                .collect(Collectors.joining(","));
```

## Group By

## Method references
