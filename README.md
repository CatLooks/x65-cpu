# X65 CPU Emulator
A C++ header file for emulating X65 CPU.

# Documentation
The following code is encapsuled in <code>x65</code> namespace.

All functions are C-styled. To create a CPU, use <code>CPU</code> structure.
It has the following attributes:
| Name | Type | Description |
| ---- | ---- | ----------- |
| <code>a</code> | Word | Accumulator |
| <code>b</code> | Word | Buffer      |
| <code>x</code> | Word | X-Index     |
| <code>y</code> | Word | Y-Index     |
| <code>i</code> | Word | Instruction Pointer |
| <code>s</code> | Word | Stack Pointer |
| <code>l</code> | Word | Stack Limiter |
| <code>p</code> | Byte | Processor Status |
| <code>halt</code> | Bool | Processor Halt |
| <code>wait</code> | Bool | Interrupt Wait |

For address mapping, use next function pointers (data transfer is 8-bits wide):
```cpp
void x65::CPU::set(word address, byte data); // output (CPU -> I/O)
byte x65::CPU::get(word address);            // input  (CPU <- I/O)
```

To clock a CPU, use <code>tick</code> function:
```cpp
void x65::tick(CPU& cpu);
```
