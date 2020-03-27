#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>
#include <bits/stdc++.h>
int main()
{
	int fd[2], nbytes;
	pid_t childpid;
	char string[] = "Hello, world!\n";
	char readbuffer[80];

	pipe(fd);

	if((childpid = fork()0 == -1)
	{
		perror("fork");
		exit(1);
	}
	if(childpid == 0 )
	{
		/* Close stdin duplicate the input side of pipe to stdin/
		dup2(0, fd[0]);
		execlp("sort", "sort", NULL);
		}
		else
		{
			/Parent process closes up output side of pipe/
			close(fd[1]);

			/Read in a string from the pipe
			*/
			nbytes = read(fd[0],
			readbuffer, sizeof(readbuffer));
			printf("Received string: %s",
			readbuffer);
			}
			return(0);
			}			
