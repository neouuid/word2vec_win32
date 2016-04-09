# About #
word2vec_win32: build google word2vec with VS2013

**You'd better build word2vec under Linux, if possible.**

# How to build #
1. download the source
2. build word2vec_win32.sln with VS2013
3. done

# What are the differences? #
1. clone all the codes from [ https://code.google.com/p/word2vec/]( https://code.google.com/p/word2vec/ "google")
2. create VS2013 solution and projects based on the makefile 
3. make some chage so VS2013 will build the exes:

----------
- add this definination to all c files
    
    \#define \_CRT\_SECURE\_NO\_WARNINGS

- change some "const" to "#define", Ex.
    
    \#define MAX\_STRING 100

- use \_aligned\_malloc to replace posix\_memalign
    
    \#define posix\_memalign(p, a, s) (((*(p)) = \_aligned\_malloc((s), (a))), *(p) ?0 :errno)
    
- add [https://www.sourceware.org/pthreads-win32/](https://www.sourceware.org/pthreads-win32/ "pthreads-win32") to project word2vec, and adjust inlude/lib path

- that's it.
