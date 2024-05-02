## Functions

### Don't

```dart
void printMessage() {
  String message = "Hello, World!";
  print(message);
}
```

### Do

```dart
void printMessage(String message) {
  print(message);
}

// Usage
printMessage("Hello, World!");
```

## Classes and Objects

### Don't

```dart
class Person {
  String name;
  int age;

  Person(String name, int age) {
    this.name = name;
    this.age = age;
  }
}
```

### Do

```dart
class Person {
  final String name;
  final int age;

  Person({required this.name, required this.age});
}

// Usage
Person person = Person(name: "John Doe", age: 30);
```

## Variables

### Don't

```dart
int? age = null;
```

### Do

```dart
int? age;

// or

int? age = 30;
```

## Naming Conventions

### Don't

```dart
class person {
  String Name;
  int aGe;

  person(this.Name, this.aGe);
}
```

### Do

```dart
class Person {
  final String name;
  final int age;

  Person({required this.name, required this.age});
}
```
