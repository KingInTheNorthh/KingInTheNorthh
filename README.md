```text
   ____  _  ___   ____      ____ _    ____ _    _ _____ ____
  / ___|| |/ / \ / /\ \    / /  / \  | |  | |  | | ____|  _ \
  \___ \| ' / \ V /  \ \/\/ / / _ \ | |  | |_/| |  _| | |_) |
   ___) | . \  | |    \  /\  / / ___ \| |__|  _  | |___|  _ <
  |____/|_|\_\ |_|     \/  \/ /_/   \_\____|_| |_|_____|_| \_\

       [ node: skywalker ]  ::  uname -a  →  not your average userland
```

```console
$ ssh skywalker@unknown-host
The authenticity of host 'unknown-host' can't be established.
Are you sure you want to continue connecting? [yes/no] yes
Warning: Permanently added 'unknown-host' to the list of known hosts.

Last login: from a rabbit hole, three commits deep.
```

---

## ┌─[ BOOT SEQUENCE ]─────────────────────────────────────────┐

```console
[    0.000000] kernel: Linux version 6.x (skywalker@thinkpad)
[    0.004211] OK   ] Mounting /curiosity ......................... done
[    0.009870] OK   ] Loading systems-level intuition ............. done
[    0.013004] OK   ] Probing memory for undefined behavior ....... 1 found
[    0.01855x] WARN ] Sleep daemon failed to start (low priority)
[    0.021118] OK   ] Initializing threat-intelligence modules ..... done
[    0.027640] OK   ] Attaching debugger to reality ............... done
[    0.031900] OK   ] Disabling abstraction layer (read-only) ...... done
[    0.044012] OK   ] Reached target: understand-how-it-works.target
[    0.050000] login: starting user session for 'skywalker'
```

---

## ┌─[ WHOAMI ]────────────────────────────────────────────────┐

```console
$ whoami --verbose

skywalker
├── systems programmer            # lives a few syscalls below comfort
├── low-level developer           # speaks C, dreams in registers
├── linux operator                # tiling wm, no mouse, no regrets
├── threat-intel apprentice       # reads the logs nobody else opens
├── offensive-security explorer   # asks "what happens if I send THIS?"
├── reverse engineer (in training)# objdump is a bedtime story
└── perpetual learner             # exit code 0 is suspicious

$ groups skywalker
tinkerers builders documentation-readers rabbit-hole-divers
```

---

## ┌─[ CURRENT INVESTIGATIONS ]────────────────────────────────┐

```text
╔══════════════════════════════════════════════════════════════╗
║  OPERATION_KERNEL                              STATUS: ACTIVE  ║
╠══════════════════════════════════════════════════════════════╣
║  > Linux internals & the syscall boundary                     ║
║  > Virtual memory, paging, and the page-fault handler         ║
║  > Process scheduling and the cost of a context switch        ║
╚══════════════════════════════════════════════════════════════╝

╔══════════════════════════════════════════════════════════════╗
║  OPERATION_REDLINE                           STATUS: ONGOING   ║
╠══════════════════════════════════════════════════════════════╣
║  > Malware behavior & static/dynamic analysis                 ║
║  > Network forensics and packet archaeology                   ║
║  > Threat intelligence: from IOC to actor profile             ║
╚══════════════════════════════════════════════════════════════╝

╔══════════════════════════════════════════════════════════════╗
║  OPERATION_TOOLSMITH                       STATUS: RECURRING   ║
╠══════════════════════════════════════════════════════════════╣
║  > Building strange CLI tools that probably shouldn't exist   ║
║  > Compilers, parsers, and the dark art of error messages     ║
╚══════════════════════════════════════════════════════════════╝
```

---

## ┌─[ TOOLCHAIN ]─────────────────────────────────────────────┐

```console
$ tree /toolchain

/toolchain
├── languages
│   ├── C            # the lingua franca of the machine
│   ├── C++          # for when C needs more rope
│   ├── Rust         # the borrow checker is my therapist
│   ├── Go           # when concurrency must just work
│   ├── Python       # glue, scripting, and quick autopsies
│   └── Bash         # everything is a pipe if you're brave enough
│
├── operating_systems
│   ├── Linux        # primary habitat
│   ├── Fedora       # daily driver
│   └── /dev/null    # where bad ideas are mounted
│
├── security
│   ├── threat-intelligence
│   ├── digital-forensics
│   ├── reverse-engineering
│   ├── malware-analysis
│   └── network-analysis
│
├── instruments
│   ├── gdb · objdump · strace · ltrace
│   ├── Wireshark · tcpdump · nmap
│   ├── Ghidra · radare2
│   └── git · make · valgrind
│
└── infrastructure
    ├── Docker · nginx · Postgres
    └── a thinkpad that has seen things
```

---

## ┌─[ SYSTEM STATUS ]─────────────────────────────────────────┐

```text
$ top -u skywalker

  PID  PROCESS                LOAD                        STATE
─────────────────────────────────────────────────────────────────────
 0001  curiosity              [#########################-]  99%   RUN
 0002  side_projects          [######################----]  87%   RUN
 0003  threat_intel_queue     [growing....................]  ++    RUN
 0004  documentation_written  [######--------------------]  23%   IDLE
 0005  caffeine_levels        [############################] 100%  CRIT
 0006  sleep                  ────────────────────────────  SEGFAULT
─────────────────────────────────────────────────────────────────────

mem:  RAM allocated mostly to "wait, how does THAT actually work?"
swap: heavy — too many browser tabs of CVE writeups
```

---

## ┌─[ ACTIVE MISSIONS ]───────────────────────────────────────┐

```console
$ ls -la /missions

drwxr-xr-x  error-translator/
    └── turns cryptic compiler & linker errors into plain human language
        target: every dev who has ever screamed at a template error

drwxr-xr-x  voiceup/
    └── citizen governance & reporting platform
        target: give people a channel that actually reaches the right desk

drwxr-xr-x  experimental-labs/
    └── systems + security research, half-finished tools, sharp edges
        target: learn by breaking, document by surviving

-rw-------  .classified/
    └── you do not have read permission for this directory
```

---

## ┌─[ NETWORK MAP ]───────────────────────────────────────────┐

```text
        [ user-space ]
             │
   ┌─────────┴─────────┐
   │   libc / syscalls │   ← where the questions start
   └─────────┬─────────┘
             │
     ╔═══════▼═══════╗
     ║  KERNEL LAND  ║  ── scheduler ── vmem ── netstack ── fs
     ╚═══════╤═══════╝
             │
   ┌─────────┴─────────┐
   │     hardware      │   ← the floor. there is no abstraction below.
   └───────────────────┘

  reach me:  mailto → asknartey@st.knust.edu.gh
  protocol:  prefers plaintext, patience, and a good writeup
```

---

## ┌─[ PHILOSOPHY ]────────────────────────────────────────────┐

```text
# ~/.config/skywalker/principles.conf

understand_before_using   = true    # a black box is just a future bug
automate_the_boring       = true    # if I did it twice, I'll script it
read_the_docs             = always  # the man page knew all along
learn_from_failure        = true    # core dumps are honest feedback
stay_curious              = 0xFFFF   # max value, no overflow check
ship_imperfect            = true    # done teaches more than perfect
```

---

## ┌─[ TELEMETRY ]─────────────────────────────────────────────┐

```console
$ git log --oneline --author=skywalker | wc -l
```

![status](https://github-readme-stats.vercel.app/api?username=KingInTheNorthh&show_icons=true&hide_border=true&theme=dark&include_all_commits=false&count_private=true&hide_title=true)

![langs](https://github-readme-stats.vercel.app/api/top-langs/?username=KingInTheNorthh&layout=compact&hide_border=true&theme=dark&langs_count=8)

---

## ┌─[ FINAL TRANSMISSION ]────────────────────────────────────┐

```console
$ logout

Connection to skywalker closed.

  ──────────────────────────────────────────────────
   If you've read this far, there's a rabbit hole
   somewhere nearby. Bring a debugger.
  ──────────────────────────────────────────────────

[ session ended ]  ::  exit code 0  ::  (suspiciously clean)
```
