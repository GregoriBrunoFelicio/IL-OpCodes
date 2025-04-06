# IL OpCodes

## 📖 About this Repository

This repository lists IL OpCodes available in the `.NET` runtime via `System.Reflection.Emit`, along with brief descriptions of what each one does at runtime.

> ⚠️ If you find any missing OpCode, feel free to open a pull request or issue to help improve this reference.

---

## 📦 Stack Management

| OpCode        | Description |
|---------------|-------------|
| `nop`         | Does nothing. Useful for debugging. |
| `pop`         | Removes the top element from the stack. |
| `dup`         | Duplicates the top element on the stack. |
| `break`       | Signals a breakpoint to a debugger. |

---

## 📥 Loading Constants

| OpCode        | Description |
|---------------|-------------|
| `ldc.i4`      | Loads a 32-bit integer constant onto the stack. |
| `ldc.i4.s`    | Loads a small int (sbyte) onto the stack. |
| `ldc.i4.0` to `ldc.i4.8` | Pushes integers 0 through 8. |
| `ldc.i4.m1`   | Pushes the value -1 onto the stack. |
| `ldc.i8`      | Loads a 64-bit integer constant. |
| `ldc.r4`      | Loads a 32-bit floating-point constant. |
| `ldc.r8`      | Loads a 64-bit floating-point constant. |

---

## 📦 Variables

| OpCode        | Description |
|---------------|-------------|
| `ldloc`       | Loads the value of a local variable onto the stack. |
| `ldloc.0` to `ldloc.3` | Loads local variables 0 through 3. |
| `stloc`       | Pops a value from the stack and stores it in a local variable. |
| `stloc.0` to `stloc.3` | Stores a value in local variables 0 through 3. |
| `ldarg`       | Loads a method argument onto the stack. |
| `ldarg.0` to `ldarg.3` | Shortcut for loading arguments 0 through 3. |
| `ldarg.s`     | Loads an argument at a specified index (short form). |
| `ldarga`      | Loads the address of a method argument. |
| `starg`       | Stores a value into an argument slot. |

---

## 📞 Method Calls

| OpCode        | Description |
|---------------|-------------|
| `call`        | Calls a method. Arguments are pushed in order, return value is pushed after the call. |
| `callvirt`    | Calls a virtual method (includes null check). |
| `calli`       | Calls a method using a function pointer. |
| `ret`         | Returns from the current method. |

---

## 🎯 Branching and Flow Control

| OpCode        | Description |
|---------------|-------------|
| `br`          | Unconditional branch to a target instruction. |
| `brtrue`      | Branches if the value is non-zero (true). |
| `brfalse`     | Branches if the value is zero (false). |
| `beq`         | Branch if equal. |
| `bne.un`      | Branch if not equal (unsigned or unordered). |
| `bgt`         | Branch if greater than. |
| `blt`         | Branch if less than. |
| `bge`         | Branch if greater than or equal. |
| `ble`         | Branch if less than or equal. |
| `switch`      | Jumps to one of several targets. |
| `leave`       | Exits a `try`, `catch`, or `finally` block. |
| `leave.s`     | Short form of `leave`. |
| `endfinally`  | Marks the end of a `finally` block. |
| `endfilter`   | Marks the end of a filter clause. |
| `rethrow`     | Rethrows the current exception. |

---

## ➕ Arithmetic and Logic

| OpCode        | Description |
|---------------|-------------|
| `add`         | Adds two values. |
| `sub`         | Subtracts two values. |
| `mul`         | Multiplies two values. |
| `div`         | Divides two values (signed). |
| `div.un`      | Divides unsigned values. |
| `rem`         | Computes remainder. |
| `and`         | Bitwise AND. |
| `or`          | Bitwise OR. |
| `xor`         | Bitwise XOR. |
| `not`         | Bitwise complement. |
| `neg`         | Negates a value. |
| `shl`         | Shifts left. |
| `shr`         | Shifts right (signed). |
| `shr.un`      | Shifts right (unsigned). |

---

## 🧪 Comparison

| OpCode        | Description |
|---------------|-------------|
| `ceq`         | Compares two values for equality. |
| `cgt`         | Compares if the first is greater than the second. |
| `cgt.un`      | Compares unsigned greater-than. |
| `clt`         | Compares if the first is less than the second. |
| `clt.un`      | Compares unsigned less-than. |

---

## 🧮 Array Operations

| OpCode        | Description |
|---------------|-------------|
| `newarr`      | Creates a new zero-based, one-dimensional array. |
| `ldlen`       | Pushes the length of an array onto the stack. |
| `ldelem`      | Loads an element from an array. |
| `ldelem.i4`   | Loads a 32-bit int from an array. |
| `stelem`      | Stores an element in an array. |
| `stelem.i4`   | Stores a 32-bit int into an array. |
| `ldelema`     | Pushes the address of an array element. |

---

## 🏗 Object Operations

| OpCode        | Description |
|---------------|-------------|
| `newobj`      | Allocates a new object and calls its constructor. |
| `ldstr`       | Loads a string literal. |
| `ldfld`       | Loads the value of a field. |
| `stfld`       | Stores a value in a field. |
| `ldsfld`      | Loads a static field. |
| `stsfld`      | Stores a static field. |
| `castclass`   | Casts an object to a class. |
| `isinst`      | Tests whether an object is an instance of a class. |
| `box`         | Boxes a value type. |
| `unbox`       | Extracts a boxed value type pointer. |
| `unbox.any`   | Unboxes a value to a value type. |
| `initobj`     | Initializes a value type to default values. |
| `cpobj`       | Copies a value type from one location to another. |
| `ldobj`       | Loads a value type from memory. |
| `stobj`       | Stores a value type to memory. |

---

## 🧱 Type Conversion

| OpCode             | Description |
|--------------------|-------------|
| `conv.i4`          | Converts value to int32. |
| `conv.i8`          | Converts value to int64. |
| `conv.i1`, `conv.i2` | Converts to smaller signed int. |
| `conv.u1`, `conv.u2`, `conv.u4`, `conv.u8` | Converts to unsigned ints. |
| `conv.r4`          | Converts to float32. |
| `conv.r8`          | Converts to float64. |
| `conv.ovf.i4`, `conv.ovf.u4` | Conversion with overflow checking. |
| `ckfinite`         | Checks whether a floating-point number is finite. |

---

## 🛠 Exception Handling

| OpCode        | Description |
|---------------|-------------|
| `throw`       | Throws an exception. |
| `leave`       | Exits a `try`, `catch`, or `finally` block. |
| `leave.s`     | Short form of `leave`. |
| `endfinally`  | Ends a finally block. |
| `endfilter`   | Ends a filter clause. |
| `rethrow`     | Rethrows the current exception. |

---

## 📌 Metadata Tokens & Function Pointers

| OpCode        | Description |
|---------------|-------------|
| `ldtoken`     | Pushes a runtime handle (metadata token) for a field, method, or type. |
| `ldftn`       | Pushes a method pointer. |
| `ldvirtftn`   | Loads the address of a virtual method (for delegates). |
| `mkrefany`    | Pushes a typed reference. |
| `arglist`     | Returns a handle to the argument list. |

---

## 📚 References

- [ECMA-335 Common Language Infrastructure (CLI)](https://www.ecma-international.org/publications-and-standards/standards/ecma-335/)
- [.NET IL OpCodes documentation](https://learn.microsoft.com/en-us/dotnet/api/system.reflection.emit.opcodes)
