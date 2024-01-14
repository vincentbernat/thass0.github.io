---
layout: post
title: The Root of the Dependency Tree
---

The hobby debugger I am working on, [Spray](https://github.com/thass0/spray), features custom syntax highlighting of C source code. To implement this, I had to recursively parse all the type definitions in the current source file and in its dependencies.

[C is not a context-free language](https://eli.thegreenplace.net/2011/05/02/the-context-sensitivity-of-cs-grammar-revisited), which leads to the so-called typedef-name problem [^1]. The problem is that `typedef` can be used to make types look like regular identifiers. This creates some situations where context is needed to determine whether the given identifier is a type. Since types and identifiers should be highlighted with different colors, I had to get that context.

While slowly iterating on the logic required to solve this problem, I got to a point where I could inspect the entire public dependency tree of all the header files included in a single source file. Header files are all I need to worry about here, since that is where all public type definitions live.

This revealed some pretty interesting patterns, some of which I have already shared on [Twitter/X](https://twitter.com/d4kdd/status/1692816506898333712?s=20). What I found most interesting is that basically every program you will every write[^2] will somehow include the `bits/wordsize.h` header file. Here is what it looks like on my machine:

```c
/* Determine the wordsize from the preprocessor defines.  */

#if defined __x86_64__ && !defined __ILP32__
# define __WORDSIZE	64
#else
# define __WORDSIZE	32
#define __WORDSIZE32_SIZE_ULONG		0
#define __WORDSIZE32_PTRDIFF_LONG	0
#endif

#ifdef __x86_64__
# define __WORDSIZE_TIME64_COMPAT32	1
/* Both x86-64 and x32 use the 64-bit system call interface.  */
# define __SYSCALL_WORDSIZE		64
#else
# define __WORDSIZE_TIME64_COMPAT32	0
#endif
```

As you can see, it simply defines the word size of the host processor. This information is then used all over the C standard library.

So, if you want your code to be used by the largest number of developers possible, contributing to this file is a great way to start!

---

[^1]: Actually, I haven't gotten around to implementing `typedef`s yet. For now it would be sufficient  to scan for `struct`, `enum`, etc. to check if something is type.

[^2]: At least if you're working on a Linux (and possibly other UNIX too) machine. But where else would one every write software, right?
