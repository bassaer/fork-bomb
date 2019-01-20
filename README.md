# fork-bomb

```
~/fork-bomb vagrant@localhost
❯ python a.py &
[1] 2684

~/fork-bomb vagrant@localhost
❯ ps auxf | grep vagrant
root      2317  0.0  0.7 100028  3968 ?        Ss   12:25   0:00  \_ sshd: vagrant [priv]
vagrant   2320  0.0  0.4 100028  2188 ?        S    12:25   0:00  |   \_ sshd: vagrant@pts/0
vagrant   2321  0.0  0.7 131236  3780 pts/0    Ss+  12:25   0:00  |       \_ -zsh
vagrant   2340  0.0  0.5 131224  2728 pts/1    Ss+  12:25   0:00  |           \_ -zsh
root      2350  0.0  0.7 100028  3964 ?        Ss   12:25   0:00  \_ sshd: vagrant [priv]
vagrant   2353  0.0  0.4 100028  2308 ?        S    12:25   0:00      \_ sshd: vagrant@pts/2
vagrant   2354  0.4  0.8 135780  4356 pts/2    Ss   12:25   0:01          \_ -zsh
vagrant   2373  0.0  0.5 131224  2732 pts/3    Ss+  12:25   0:00              \_ -zsh
vagrant   2684  0.0  0.7 117184  3788 pts/2    S    12:30   0:00              \_ python a.py
vagrant   2685  0.0  0.4 117184  2300 pts/2    S    12:30   0:00              |   \_ python a.py
vagrant   2695  1.0  0.2 110356  1128 pts/2    R+   12:30   0:00              \_ ps auxf
```

```
❯ python b.py &
[1] 2973
Traceback (most recent call last):
  File "b.py", line 4, in <module>
    os.fork()
OSError: [Errno 11] Resource temporarily unavailable
Traceback (most recent call last):
  File "b.py", line 4, in <module>
    os.fork()
OSError: [Errno 11] Resource temporarily unavailable
Traceback (most recent call last):
  File "b.py", line 4, in <module>
    os.fork()
OSError: [Errno 11] Resource temporarily unavailable
```
