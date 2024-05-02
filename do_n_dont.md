
## Stateless Widgets

### Don't

```dart
class MyWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container(
      child: Text("Hello, World!"),
    );
  }
}
```

### Do

```dart
class MyWidget extends StatelessWidget {
  final String text;

  MyWidget({required this.text});

  @override
  Widget build(BuildContext context) {
    return Container(
      child: Text(text),
    );
  }
}

// Usage
MyWidget(text: "Hello, World!");
```

## Stateful Widgets

### Don't

```dart
class MyStatefulWidget extends StatefulWidget {
  @override
  _MyStatefulWidgetState createState() => _MyStatefulWidgetState();
}

class _MyStatefulWidgetState extends State<MyStatefulWidget> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Counter"),
      ),
      body: Center(
        child: Text("$_counter"),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        child: Icon(Icons.add),
      ),
    );
  }
}
```

### Do

```dart
class MyStatefulWidget extends StatefulWidget {
  @override
  _MyStatefulWidgetState createState() => _MyStatefulWidgetState();
}

class _MyStatefulWidgetState extends State<MyStatefulWidget> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Counter"),
      ),
      body: Center(
        child: Text(
          "$_counter",
          style: Theme.of(context).textTheme.headline4,
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        child: const Icon(Icons.add),
      ),
    );
  }
}
```

## ListView

### Don't

```dart
ListView(
  children: [
    ListTile(
      title: Text("Item 1"),
    ),
    ListTile(
      title: Text("Item 2"),
    ),
    ListTile(
      title: Text("Item 3"),
    ),
  ],
)
```

### Do

```dart
ListView.builder(
  itemCount: 3,
  itemBuilder: (context, index) {
    return ListTile(
      title: Text("Item ${index + 1}"),
    );
  },
)
```

## Building Widgets

### Don't

```dart
Widget _buildWidget() {
  return Container(
    child: Text("Hello, World!"),
  );
}
```

### Do

```dart
Widget _buildWidget(String text) {
  return Container(
    child: Text(text),
  );
}

// Usage
_buildWidget("Hello, World!");
```

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
