# syzkaller - kernel fuzzer

This repository contains our modified verison of syzkaller, adapted for improved io_uring coverage.
We also included the used linux config file ".config".
We mainly modified the file sys/linux/io_uring.txt, since it contains the relevant syscall descriptions.

We ran syzkaller with two different configs: Once with only io_uring related syscalls enabled and once with all syscalls enabled.
For this we used the config files "manager-config-uring_only.cfg" and "manager-config-all.cfg" respectively.
There outputs are in the directories "workdir_uring_only" and "workdir_all".
These directories also contain our accumulated corpus and crashes mentioned in the report.
The corpuses are only available in unpacked form, due to file size limitations.
A corpus file can be create using the syz-db tool.
Extracted coverage information produced using "manager-config-all.cfg" is stored in the results directory.