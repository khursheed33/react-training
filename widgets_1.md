Stateless Widgets: Don't
------------------------

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

Stateless Widgets: Do
---------------------

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

Stateful Widgets: Don't
------------------------

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

Stateful Widgets: Do
---------------------

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

ListView: Don't
----------------

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

ListView: Do
-------------

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

Building Widgets: Don't
-----------------------

```dart
Widget _buildWidget() {
  return Container(
    child: Text("Hello, World!"),
  );
}
```

Building Widgets: Do
--------------------

```dart
Widget _buildWidget(String text) {
  return Container(
    child: Text(text),
  );
}

// Usage
_buildWidget("Hello, World!");
```
