The design of EasyCrash based on crash and restart tests in NVMM. Leveraging [Non-Volatile Memory Crash Tester](https://github.com/NVMCrashTester/NVCT) user can launch a number of crash tests simultaneously with linux [screen](https://linuxize.com/post/how-to-use-linux-screen/). 

Step 1: Launch crash tests.
  Before launch a set of crash test, NVCT and application need to be modified accordingly. The details can be found in README in NVCT.
  User can launch a crash test by execute `sh run.sh /path/to/application` or a number of crash tests simultaneously by execute `sh screen_run`. To change the number of crash tests and the application use in crash tests, user can modify screen.sh.
 
Step 2: Collect crash tests result.
  The Intel PIN can cause 30x to 2000x slow down. It may take a while to finish crash tests. Once the crash tests finished, user can execute `python gether_result.py` to collect crash tests result and execute 'auto_recompute' to resume the application based on crash tests result. The data inconsistent rate of candicactes of critical data objects and application recomputability can be found in file "result_pid#.txt"  
  
TIPS:
1. The intermediate result between step 1 and step 2 can achieve few GB or even more since NVCT dump the values from simulated main memory and simulated cache. 

