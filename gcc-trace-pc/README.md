# Trace-pc in gcc

`Trace-pc` flag will insert a call to `__sanitizer_cov_trace_pc` into every basic block[^1], so it calculates basic block coverage. This support to gcc perhaps added from version 6.0[^2]. Kcov use this feature to get kernel coverage and implement `__sanitizer_cov_trace_pc` in `kernel/kcov.c`[^3]. Here we use `trace-pc` flag in user mode[^4].

[^1]: https://gcc.gnu.org/onlinedocs/gcc/Instrumentation-Options.html
[^2]: https://gcc.gnu.org/legacy-ml/gcc-patches/2015-12/msg00299.html
[^3]: https://github.com/torvalds/linux/commit/5c9a8750a6409c63a0f01d51a9024861022f6593
[^4]: https://davejingtian.org/2017/06/01/understanding-kcov-play-with-fsanitize-coveragetrace-pc-from-the-user-space/