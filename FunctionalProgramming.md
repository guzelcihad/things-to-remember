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

## Method references
