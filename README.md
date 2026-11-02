# Assignment 5 Strategy Pattern

A simple Java calculator using the Strategy pattern. The same calculator switches between addition, subtraction, and multiplication while the program is running.

## Requirements

JDK 17. No external libraries or build tools are required.

## Files

| Location | Purpose |
| --- | --- |
| `src/OperationStrategy.java` | Common interface for arithmetic operations |
| `src/AddStrategy.java` | Addition |
| `src/SubtractStrategy.java` | Subtraction |
| `src/MultiplyStrategy.java` | Multiplication |
| `src/Calculator.java` | Context that stores and calls the current strategy |
| `src/Main.java` | Client that selects and switches strategies |
| `examples/` | Separate example of adding a power operation |
| `REPORT.md` | Assignment reflection, UML, and Clean Code examples |

## Run in IntelliJ IDEA

1. Extract the archive and open the `assignment5-strategy` folder.
2. In **File > Project Structure > Project**, select **JDK 17**.
3. If needed, right-click `src` and choose **Mark Directory as > Sources Root**.
4. Open `src/Main.java` and run its `main` method.

## Build and run from a terminal

Open a terminal in the project folder:

```bash
javac --release 17 -d out src/*.java
java -cp out Main
```

Expected output:

```text
Addition: 15.0
Subtraction: 5.0
Multiplication: 50.0
```

`Main` creates one `Calculator`, then calls `setStrategy` twice. `Calculator` delegates to `OperationStrategy.execute` without checking the operation type.

## Add a new strategy

1. Create a class implementing `OperationStrategy`.
2. Put the new algorithm in `execute`.
3. Pass an instance to `Calculator` or call `setStrategy` in the client.

The `examples` folder demonstrates this with `PowerStrategy` and a new client, `PowerDemo`. All existing classes in `src` stay unchanged.

```bash
javac --release 17 -d out src/*.java examples/*.java
java -cp out PowerDemo
```

Expected output:

```text
2 + 3 = 5.0
2 ^ 3 = 8.0
```

To run this example in IntelliJ, also mark `examples` as a **Sources Root**, then run `PowerDemo.main`.
