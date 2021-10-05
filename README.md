##### VirtualAlloc - allocate memory with the current process, the size of the shellcode and assign the permissions RWX (0x40)
##### RtlMoveMemory - copy the shellcode in the space allocated by the memory allocation.
##### CreateThread - Create the thread which execute the shellcode allocated before into the memory
##### WaitForSingleObject - tell the thread to wait until the thread created exits so don't want your beacon session lost.

---------------------------------------------------------------------------------------------------------------------------------------------------

##### VirtualAlloc - allocate memory with the current process, the size of the shellcode and assign the permissions RW (not executable) (0x4)
##### RtlMoveMemory - copy the shellcode in the space allocated by the memory allocation.
##### Virtualprotect - change memory space on executable - X (0x10)
##### CreateThread - Create the thread which execute the shellcode allocated before into the memory
##### WaitForSingleObject - tell the thread to wait until the thread created exits so don't want your beacon session lost.

---------------------------------------------------------------------------------------------------------------------------------------------------
At this point permissions RWX has been deleted from the memory. This include the function VirtualProtect (UNFORTUNATLY the function is not widly used) so you can track it.
Instead use VirtualAlloc to allocate memory space, you can use HeapCreate. You need to assign to this memory space RWX.
You can use different primitive win calls to bypass AV/ Detection tools.


