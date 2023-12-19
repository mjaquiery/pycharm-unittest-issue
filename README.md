# Minimal repository for demonstrating testing issues

## Setup

1. Build docker container with `docker-compose build`
2. Note successful output from `docker-compose run --rm harvester_test`
3. Set up a run configuration with Python tests > Unittest
   - Set target to 'Custom'
4. Run the configuration
5. Note that the tests fail with the following error:

```shell
/usr/local/bin/python3 /opt/.pycharm_helpers/pycharm/_jb_unittest_runner.py 
Testing started at 09:24 ...
Starting tmp_harvester_test_1 ... 
Starting tmp_harvester_test_1 ... done
Attaching to tmp_harvester_test_1
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
Windows named pipe error: The pipe has been ended. (code: 109)

Process finished with exit code 1

Empty suite
```

Incidentally, note also that running the configuration again generates the same output but with many more errors:

```shell
/usr/local/bin/python3 /opt/.pycharm_helpers/pycharm/_jb_unittest_runner.py 
Testing started at 09:25 ...
tmp_harvester_test_1 is up-to-date
Attaching to tmp_harvester_test_1
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
[... 600 lines ommitted ...]
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
harvester_test_1  | SyntaxError: Non-UTF-8 code starting with '\xe2' in file /usr/local/bin/python3 on line 2, but no encoding declared; see https://python.org/dev/peps/pep-0263/ for details
tmp_harvester_test_1 exited with code 1
Stopping tmp_harvester_test_1 ... 
Stopping tmp_harvester_test_1 ... done
1
Aborting on container exit...

Process finished with exit code 1

Empty suite
```

## PyCharm details

PyCharm 2023.3.1 (Professional Edition)
Build #PY-233.11799.298, built on December 12, 2023
Licensed to Matt Jaquiery
Subscription is active until January 4, 2024.
For educational use only.
Runtime version: 17.0.9+7-b1087.7 amd64
VM: OpenJDK 64-Bit Server VM by JetBrains s.r.o.
Windows 10.0
GC: G1 Young Generation, G1 Old Generation
Memory: 4096M
Cores: 16
Registry:
  ide.experimental.ui=true
Non-Bundled Plugins:
  com.mzyupc.a-redis (1.0.0)
  com.github.copilot (1.4.5.4049)
  com.intellij.ideolog (222.2.0.0)
  com.godwin.json.parser (1.7.1)
  org.plugin.dot.id (1.5.3)
  dev.meanmail.plugin.nginx-intellij-plugin (2022.1.1)
  com.schwarzit.spectral-intellij-plugin (3.0.1)
  com.intellij.kubernetes (233.11799.296)
  net.seesharpsoft.intellij.plugins.csv (3.2.3-233)
  com.intellij.ml.llm (233.11799.300)
  ru.adelf.idea.dotenv (2023.3)
  SnakeCharm (2023.3.1)
  mobi.hsz.idea.gitignore (4.5.2)
