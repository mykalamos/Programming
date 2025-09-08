# Volatile

- Different threads may keep their own cached copies of variables for performance.

- Without volatile, one thread might never see changes made by another thread immediately, leading to subtle bugs.

Marking a field as volatile tells the runtime to:

- Always read the latest value from main memory.
- Always write changes back immediately.
- Avoid certain kinds of compiler and CPU optimizations that assume single-threaded access.