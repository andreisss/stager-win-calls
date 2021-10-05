### VirtualAlloc - allocate memory with the current process, the size of the shellcode and assign the permissions RWX
### RtlMoveMemory - copy the shellcode in the space allocated by the memory allocation.
### CreateThread - Create the thread which execute the shellcode allocated before into the memory
### WaitForSingleObject - tell the thread to wait until the thread created exits so don't want your beacon session lost.
