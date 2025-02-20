# bootstrapping a compiler from scratch

okay... that's not that impressive since you have a programming language li–

# from scratch

okay, so you're writing a small compiler in assembly, assembling it with nasm, an–

# from scratch

oh dear

## Rules

Each phase has a directory associated with it, starting with 0. The output of each phase will be an executable of the same name (for example, `./0/0`). Each
stage will build upon previous stages to slowly build up more functionality. The only thing I'm allowed to write executables with is a hex editor for stage 0
to get started, and then my previous executables. Input/output redirection is used with these executables to generate what is needed.

## System

This project was developed on an x86_64 Arch Linux system:

```
$ lscpu
Architecture:             x86_64
  CPU op-mode(s):         32-bit, 64-bit
  Address sizes:          39 bits physical, 48 bits virtual
  Byte Order:             Little Endian
CPU(s):                   8
  On-line CPU(s) list:    0-7
Vendor ID:                GenuineIntel
  Model name:             Intel(R) Xeon(R) E-2334 CPU @ 3.40GHz
    CPU family:           6
    Model:                167
    Thread(s) per core:   2
    Core(s) per socket:   4
    Socket(s):            1
    Stepping:             1
    BogoMIPS:             6816.00
    Flags:                fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx pdpe1gb rdtscp
                           lm constant_tsc art arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc cpuid aperfmperf tsc_known_freq pni pclmulqdq dtes64 monitor ds_cp
                          l vmx smx est tm2 ssse3 sdbg fma cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic movbe popcnt tsc_deadline_timer aes xsave avx f16c rdrand lahf_lm abm 3
                          dnowprefetch cpuid_fault ssbd ibrs ibpb stibp ibrs_enhanced tpr_shadow flexpriority ept vpid ept_ad fsgsbase tsc_adjust bmi1 avx2 smep bmi2 erms
                          invpcid mpx avx512f avx512dq rdseed adx smap avx512ifma clflushopt intel_pt avx512cd sha_ni avx512bw avx512vl xsaveopt xsavec xgetbv1 xsaves dthe
                          rm ida arat pln pts vnmi avx512vbmi umip pku ospke avx512_vbmi2 gfni vaes vpclmulqdq avx512_vnni avx512_bitalg avx512_vpopcntdq rdpid fsrm md_cle
                          ar flush_l1d arch_capabilities
```

