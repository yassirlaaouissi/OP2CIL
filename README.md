# OP2CIL
A converter from opcodes to CIL instructions, made because I cried during flareon9. May contain bugs, so please make issue if you feel the need for it to be fixed.



## Usage
```
[yassir@fedora OP2CIL]$ python3 main.py randombinary.exe 0x00,0x02,0x73,0xe5,0x00,0x00,0x0a,0x0a,0x06,0x16,0x6f,0xa3,0x00,0x00,0x0a,0x6f,0xa4,0x00,0x00,0x0a,0x6f,0xe6,0x00,0x00,0x0a,0x0b,0x07,0x28,0xb3,0x00,0x00,0x06,0x0c,0x08,0x28,0xb9,0x00,0x00,0x06,0x0d,0x1a,0x8d,0x2f,0x00,0x00,0x01,0x25,0xd0,0x40,0x01,0x00,0x04,0x28,0x92,0x00,0x00,0x0a,0x09,0x28,0x80,0x00,0x00,0x06,0x13,0x04,0x11,0x04,0x07,0x03,0x28,0xb5,0x00,0x00,0x06,0x13,0x05,0x11,0x05,0x13,0x06,0x2b,0x00,0x11,0x06,0x2a
```
## Output
```
 .d88888b.  8888888b.   .d8888b.   .d8888b. 8888888 888      
d88P" "Y88b 888   Y88b d88P  Y88b d88P  Y88b  888   888      
888     888 888    888        888 888    888  888   888      
888     888 888   d88P      .d88P 888         888   888      
888     888 8888888P"   .od888P"  888         888   888      
888     888 888        d88P"      888    888  888   888      
Y88b. .d88P 888        888"       Y88b  d88P  888   888      
 "Y88888P"  888        888888888   "Y8888P" 8888888 88888888
    
-----------------------------------------------------
Supplied bytecode/opcode: 

0x00,0x02,0x73,0xe5,0x00,0x00,0x0a,0x0a,0x06,0x16,0x6f,0xa3,0x00,0x00,0x0a,0x6f,0xa4,0x00,0x00,0x0a,0x6f,0xe6,0x00,0x00,0x0a,0x0b,0x07,0x28,0xb3,0x00,0x00,0x06,0x0c,0x08,0x28,0xb9,0x00,0x00,0x06,0x0d,0x1a,0x8d,0x2f,0x00,0x00,0x01,0x25,0xd0,0x40,0x01,0x00,0x04,0x28,0x92,0x00,0x00,0x0a,0x09,0x28,0x80,0x00,0x00,0x06,0x13,0x04,0x11,0x04,0x07,0x03,0x28,0xb5,0x00,0x00,0x06,0x13,0x05,0x11,0x05,0x13,0x06,0x2b,0x00,0x11,0x06,0x2a
-----------------------------------------------------
Your CIL instructions are: 

0x00 // nop , Do nothing (No operation).
0x02 // ldarg.0 , Load argument 0 onto the stack.
0x73 // newobj <ctor> , Allocate an uninitialized object or value type and call ctor.
   Arguments:  0xe5 0x00 0x00 0x0a

0x0A // stloc.0 , Pop a value from stack into local variable 0.
0x06 // ldloc.0 , Load local variable 0 onto stack.
0x16 // ldc.i4.0 , Push 0 onto the stack as int32.
0x6F // callvirt <method> , Call a method associated with an object.
   Arguments:  0xa3 0x00 0x00 0x0a

0x6F // callvirt <method> , Call a method associated with an object.
   Arguments:  0xa4 0x00 0x00 0x0a

0x6F // callvirt <method> , Call a method associated with an object.
   Arguments:  0xe6 0x00 0x00 0x0a

0x0B // stloc.1 , Pop a value from stack into local variable 1.
0x07 // ldloc.1 , Load local variable 1 onto stack.
0x28 // call <method> , Call method described by method.
   Arguments:  0xb3 0x00 0x00 0x06

0x0C // stloc.2 , Pop a value from stack into local variable 2.
0x08 // ldloc.2 , Load local variable 2 onto stack.
0x28 // call <method> , Call method described by method.
   Arguments:  0xb9 0x00 0x00 0x06

0x0D // stloc.3 , Pop a value from stack into local variable 3.
0x1A // ldc.i4.4 , Push 4 onto the stack as int32.
0x8D // newarr <etype> , Create a new array with elements of type etype.
   Arguments:  0x2f 0x00 0x00 0x01

0x25 // dup , Duplicate the value on the top of the stack.
0xD0 // ldtoken <token> , Convert metadata token to its runtime representation.
   Arguments:  0x40 0x01 0x00 0x04

0x28 // call <method> , Call method described by method.
   Arguments:  0x92 0x00 0x00 0x0a

0x09 // ldloc.3 , Load local variable 3 onto stack.
0x28 // call <method> , Call method described by method.
   Arguments:  0x80 0x00 0x00 0x06

0x13 // stloc.s <uint8 (indx)> , Pop a value from stack into local variable indx, short form.
   Arguments:  0x04

0x11 // ldloc.s <uint8 (indx)> , Load local variable of index indx onto stack, short form.
   Arguments:  0x04

0x07 // ldloc.1 , Load local variable 1 onto stack.
0x03 // ldarg.1 , Load argument 1 onto the stack.
0x28 // call <method> , Call method described by method.
   Arguments:  0xb5 0x00 0x00 0x06

0x13 // stloc.s <uint8 (indx)> , Pop a value from stack into local variable indx, short form.
   Arguments:  0x05

0x11 // ldloc.s <uint8 (indx)> , Load local variable of index indx onto stack, short form.
   Arguments:  0x05

0x13 // stloc.s <uint8 (indx)> , Pop a value from stack into local variable indx, short form.
   Arguments:  0x06

0x2B // br.s <int8 (target)> , Branch to target, short form.
   Arguments:  0x00

0x00 // nop , Do nothing (No operation).
0x11 // ldloc.s <uint8 (indx)> , Load local variable of index indx onto stack, short form.
   Arguments:  0x06

0x2A // ret , Return from method, possibly with a value.
```

## links
- Blue bird app: https://twitter.com/kladblokje_88
- Discord: kladblokje_88#1337
