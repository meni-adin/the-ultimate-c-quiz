The user can still invoke some code after calling `exit` by registering a function to `atexit`, so he can call `exit` from such function.
