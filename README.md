Simple casting method for USTRUCTs within unreal engine. To setup all you have to do is copy the code from Struct-Cast and paste it in an accessible area within your project. I recommend setting it up as a static function.

To use: you'd use it like a regular cast but its important you make your structs a pointer first and then dereference them when its time to use


For example: 

```
FChildStruct child = ...; //(arbitrary) 

FParentStruct* castStruct = Cast<FParentStruct>(*child); //its important that they are both pointers, use '*' as a way of referencing the child struct as a pointer

FParentStruct parent = *castStruct; //Dereference the pointer from the cast

...Remaining logic

```

Something to note: Its wise to go about using this with caution, because struct pointers are not handled by garbage collection and you will run into issues if you dont properly dereference struct pointers

Enjoy! Created this as a system to write more generic style save functions, if you have any issues let me know! 
