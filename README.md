# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise

### NAME: Yamuna M
### REG NO: 212223230248

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
	return 0; }


```
## OUTPUT
![image](https://github.com/user-attachments/assets/a7cad2b6-63d6-424d-837a-743424b8f519)

## C Program to create new process using Linux API system calls fork() and exit()

```
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
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
![image](https://github.com/user-attachments/assets/9b27b090-f21f-4fbb-ba67-ffcb658cb377)


## C Program to execute Linux system commands using Linux API system calls exec() family

```

#include <stdio.h>
#include <unistd.h>
#include <stdlib.h>
#include <sys/wait.h>
#include <sys/types.h>
int main()
{       int status;
        printf("Running ps with execlp\n");
        execl("ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
printf("Running ps with execlp. Now with path specified\n");
        execl("/bin/ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
        exit(0);}//C Program to execute Linux system commands using Linux API system calls exec() family



```

## OUTPUT
![image](https://github.com/user-attachments/assets/95a57541-5eab-42d8-a3cc-f77eac15e03f)
![image](https://github.com/user-attachments/assets/0ee34ef7-af2a-48bb-a4c5-0dd60544131b)
![image](https://github.com/user-attachments/assets/29d244ec-889a-4951-b14e-d735a82da089)
![image](https://github.com/user-attachments/assets/41034540-d95d-4cd6-b33c-205e4b8e4719)
![image](https://github.com/user-attachments/assets/03649f03-0814-47a8-b1f2-6729d09c996f)
![image](https://github.com/user-attachments/assets/18aae203-bd14-4a46-bf1d-db95000c30e4)



# RESULT:
The programs are executed successfully.
