# Python-And-C-Fun-Program

One day I am running C++ code using python Script. Then I had an idea, why we can run Python code in C++. then i run same python code to run c++ code ,before run this python code I changed some In My C++ program that is `system('<now_running_python_code>.py');`, and the program is not terminated,it was while running without Loop. 

>**It was New example of How to while run your code without using loop**😅


 This is `run_cpp.py` file
```python
#run_cpp.py
import os
    os.system('g++ run_py.cpp -o run_py')
    os.system('./run_py')
   
```
the above program compile and run the run_py.cpp

In the `run_py.cpp` file
```cpp
using namespace std;

int main() {
    system("python run_cpp.py");
    return 0;
}

```

>And What happen?

# Answer is 

Each Program not fully completed!
**See This Diagram**<br>
<img src="https://i.stack.imgur.com/bnFDM.jpg" width="60%" align="left"><br>
Each program run its code recursively. So the Each program creates a parent and child program.

When your are while running this program, may be system will be crashes.

See the System Processes 
```bash
vaitheeswaran@Linux:~$ ps -a
    PID TTY          TIME CMD
 226102 pts/1    00:00:00 python
 226109 pts/1    00:00:00 sh
 226110 pts/1    00:00:00 run_py
 226111 pts/1    00:00:00 sh
 226112 pts/1    00:00:00 python
 226127 pts/1    00:00:00 sh
 226128 pts/1    00:00:00 run_py
 226129 pts/1    00:00:00 sh
 226130 pts/1    00:00:00 python
 226131 pts/1    00:00:00 sh
 226132 pts/1    00:00:00 g++
 226136 pts/3    00:00:00 ps

```
5 second later

```bash
vaitheeswaran@Linux:~$ ps -a
    PID TTY          TIME CMD
 226102 pts/1    00:00:00 python
 226109 pts/1    00:00:00 sh
 226110 pts/1    00:00:00 run_py
 226111 pts/1    00:00:00 sh
 226112 pts/1    00:00:00 python
 226127 pts/1    00:00:00 sh
 226128 pts/1    00:00:00 run_py
 226129 pts/1    00:00:00 sh
 226130 pts/1    00:00:00 python
 226140 pts/1    00:00:00 sh
 226141 pts/1    00:00:00 run_py
 226142 pts/1    00:00:00 sh
 226143 pts/1    00:00:00 python
 226151 pts/1    00:00:00 sh
 226152 pts/1    00:00:00 run_py
 226153 pts/1    00:00:00 sh
 226154 pts/1    00:00:00 python
 226162 pts/1    00:00:00 sh
 226163 pts/1    00:00:00 run_py
 226164 pts/1    00:00:00 sh
 226165 pts/1    00:00:00 python
 226173 pts/1    00:00:00 sh
 226174 pts/1    00:00:00 run_py
 226175 pts/1    00:00:00 sh
 226176 pts/1    00:00:00 python
 226229 pts/1    00:00:00 sh
 226230 pts/1    00:00:00 run_py
 226232 pts/1    00:00:00 sh
 226237 pts/1    00:00:00 python
 226869 pts/1    00:00:00 sh
 226870 pts/1    00:00:00 run_py
 226871 pts/1    00:00:00 sh
 226872 pts/1    00:00:00 python
 226880 pts/1    00:00:00 sh
 226881 pts/1    00:00:00 run_py
 226882 pts/1    00:00:00 sh
 226883 pts/1    00:00:00 python
 226891 pts/1    00:00:00 sh
 226892 pts/1    00:00:00 run_py
 226893 pts/1    00:00:00 sh
 226894 pts/1    00:00:00 python
 226902 pts/1    00:00:00 sh
 226903 pts/1    00:00:00 run_py
 226904 pts/1    00:00:00 sh
 226905 pts/1    00:00:00 python
 226914 pts/1    00:00:00 sh
 226915 pts/1    00:00:00 run_py
 226916 pts/1    00:00:00 sh
 226917 pts/1    00:00:00 python
 226925 pts/1    00:00:00 sh
 226926 pts/1    00:00:00 run_py
 226927 pts/1    00:00:00 sh
 226928 pts/1    00:00:00 python
 226937 pts/1    00:00:00 sh
 226938 pts/1    00:00:00 run_py
 226939 pts/1    00:00:00 sh
 226940 pts/1    00:00:00 python
 226941 pts/1    00:00:00 sh
 226942 pts/1    00:00:00 g++
 226943 pts/1    00:00:00 cc1plus
 226945 pts/3    00:00:00 ps

```

So, You can't stop this program using `Ctrl+C`. 
**You can Only Stop it on using Close the terminal window or unplug the system power.**
