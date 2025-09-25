# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

## C Program to print process ID and parent Process ID using Linux API system calls
```
      #include <stdio.h>
      #include <sys/types.h>
      #include <unistd.h>
      int main(void)
      {	//variable to store calling function's process id
      	pid_t process_id;
      	//variable to store parent function's process id
      	pid_t p_process_id;
      	//getpid() - will return process id of calling function
      	process_id = getpid();
      	//getppid() - will return process id of parent function
      	p_process_id = getppid();
      	//printing the process ids
      
      //printing the process ids
      	printf("The process id: %d\n",process_id);
      	printf("The process id of parent function: %d\n",p_process_id);
      	return 0;
        }
```
## OUTPUT 

<img width="889" height="250" alt="Screenshot from 2025-09-22 10-37-34" src="https://github.com/user-attachments/assets/ebb17cbf-b44a-4940-a936-c9c008034230" />


## C Program to create new process using Linux API system calls fork() and exit()
```
    #include <stdio.h>
    #include<stdlib.h>
    int main()
    { int pid; 
    pid=fork(); 
    if(pid == 0) 
    { printf("Iam child my pid is %d\n",getpid()); 
    printf("My parent pid is:%d\n",getppid()); 
    exit(0); } 
    else{ 
    printf("I am parent, my pid is %d\n",getpid()); 
    sleep(100); 
    exit(0);} 
    }
```

## OUTPUT



<img width="818" height="100" alt="Screenshot from 2025-09-22 10-46-04" src="https://github.com/user-attachments/assets/e64df19f-584f-4cc7-92b3-5d078501e1f2" />





## C Program to execute Linux system commands using Linux API system calls exec() , exit() , wait() family

```
    #include <unistd.h>
    #include <stdio.h>
    #include <stdlib.h>
    int main()
    {
    	printf("Running ps with execlp\n");
    	execlp("ps", "ps", "ax", NULL);
    	printf("Done.\n");
    	exit(0);
    }
```

## OUTPUT

<img width="844" height="712" alt="Screenshot from 2025-09-22 10-49-14" src="https://github.com/user-attachments/assets/fa1cdabb-7115-4b4b-b60e-668be1d1a5fc" />



# RESULT:
The programs are executed successfully.
