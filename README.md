# OP2CIL
A converter from opcodes to CIL instructions, made because I cried during flareon9



## Usage
```
python3 OP2CLI.py "0x00,0x02,0x73,0xe5,0x00,0x00,0x0a,0x0a,0x06,0x16,0x6f,0xa3,0x00,0x00,0x0a,0x6f,0xa4,0x00,0x00,0x0a,0x6f,0xe6,0x00,0x00,0x0a,0x0b,0x07,0x28,0xb3,0x00,0x00,0x06,0x0c,0x08,0x28,0xb9,0x00,0x00,0x06,0x0d,0x1a,0x8d,0x2f,0x00,0x00,0x01,0x25,0xd0,0x40,0x01,0x00,0x04,0x28,0x92,0x00,0x00,0x0a,0x09,0x28,0x80,0x00,0x00,0x06,0x13,0x04,0x11,0x04,0x07,0x03,0x28,0xb5,0x00,0x00,0x06,0x13,0x05,0x11,0x05,0x13,0x06,0x2b,0x00,0x11,0x06,0x2a"
```
## Output
```
0x00 // No OPeration (NOP)

0x02 // ldarg.0 = Load argument 0 onto the stack.

0x73 // newobj <ctor> = Allocate an uninitialized object or value type and call ctor. CTOR = Constructor. The constructor identifier (<ctor>) is 0xe5,0x00,0x00,0x0a in this case. Which is 0a0000e5.0xA0000E5 = StackTrace | .ctor | hasthis System.Void (System.Exception)

0x0a // stloc.0 = Pop a value from stack into local variable 0.

0x06 // ldloc.0 = Load local variable 0 onto stack.

0x16 // ldc.i4.0 = Push 0 onto the stack as int32.

0x6f // callvirt <method> = Call a method associated with an object. The method they call = 0xa3,0x00,0x00,0x0a = 0a0000a3 0xA0000A3 = StackTrace | GetFrame | hasthis System.Diagnostics.StackFrame (System.Int32)

0x6f // callvirt <method> = Call a method associated with an object. The method they call = 0xa4,0x00,0x00,0x0a = 0a0000a4 0xA0000A4 = StackTrace | GetMethod | hasthis System.Reflection.MethodBase()

0x6f // callvirt <method> = Call a method associated with an object. The method they call = 0xe6,0x00,0x00,0x0a = 0a0000e6 0xA0000E6 = MemberInfo | get_MetadataToken | hasthis System.Int32()

0x0B // stloc.1 = Pop a value from stack into local variable 1.

0x07 // ldloc.1 = Load local variable 1 onto stack.

0x28 // call <method> =  Call method described by method. Method that is called = 0xb3,0x00,0x00,0x06 = 060000b3 0x60000B3 = FLARE15.flare_66 | System.String (System.Int32) | t

0x0C // stloc.2 Pop a value from stack into local variable 2.

0x08 // ldloc.2 = Load local variable 2 onto stack.

0x28 // call <method> =  Call method described by method. Method that is called = 0xb9,0x00,0x00,0x06 = 060000b9 0x60000B9 = FLARE15.flare_69 | System.Byte[] (System.String) | h

0x0D // stloc.3 = Pop a value from stack into local variable 3.

0x1A // ldc.i4.4 = Push 4 onto the stack as int32.

0x8D // newarr <etype> Create a new array with elements of type etype. The array it makes are filled with 0x2f,0x00,0x00,0x01 = 2f000001 = 0100002f = 0x100002F = Byte (used in ToString())

0x25 // dup = Duplicate the value on the top of the stack.

0xD0 // ldtoken <token> = Convert metadata token to its runtime representation. The input to convert = 0x40,0x01,0x00,0x04 = 40010004 = 04000140 --> 0x4000140 = internal static readonly int C91849C78D4D52D51AE27BD136F927AE1418705C0A2BC9066D6F38125967F602;

0x28 // call <method> =  Call method described by method. Method that is called = 0x92,0x00,0x00,0x0a = 0a000092 0xA000092 = RuntimeHelpers | InitializeArray | System.Void(System.Array, System.RuntimeFieldHandle)

0x09 // ldloc.3 = Load local variable 3 onto stack.

0x28 // call <method> =  Call method described by method. Method that is called = 0x80,0x00,0x00,0x06 = 06000080 0x6000080 = FLARE15.flare_46 | System.Byte[] (System.Byte[], System.Byte[]) | p

0x13 // stloc.s <uint8 (indx)> = Pop a value from stack into local variable indx, short form. indx = 0x04, also known as decimal 4

0x11 // ldloc.s <uint8 (indx)> = Load local variable of index indx onto stack, short form. indx = 0x04, also known as decimal 4

0x07 // ldloc.1 = Load local variable 1 onto stack.

0x03 // ldarg.1 = Load argument 1 onto the stack.

0x28 // call <method> =  Call method described by method. Method that is called = 0xb5,0x00,0x00,0x06 = 060000b5 0x60000B5 = FLARE15.flare_67 | System.Object (System.Byte[], System,Int32, System.Object[]) | b

0x13 // stloc.s <uint8 (indx)> = Pop a value from stack into local variable indx, short form. indx = 0x05, also known as decimal 5

0x11 // ldloc.s <uint8 (indx)> = Load local variable of index indx onto stack, short form. indx = 0x05, also known as decimal 5

0x13 // stloc.s <uint8 (indx)> = Pop a value from stack into local variable indx, short form. indx = 0x06, also known as decimal 6

0x2B // br.s <int8 (target)> = Branch to target, short form. target = 0x00 = 0

0x11 // ldloc.s <uint8 (indx)> = Load local variable of index indx onto stack, short form. indxx = 0x06 = 6

0x2A // RET, return, END of method
```

## links
- Blue bird app: https://twitter.com/kladblokje_88
- Discord: kladblokje_88#1337
