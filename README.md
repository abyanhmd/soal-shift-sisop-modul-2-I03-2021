## Modul 2 - Group I03 
</br>

### **Number 1**
The problem number 1 is not completed actually. Here are the examplanation of what is already done.
The problem ask to download files from the link that is provided and store them in a new directory called Musyik for mp3, Fylm for mp4, and Pyoto for jpg. </br>
When the time is 6 hours before 22.22 WIB on 9 April, all of the folder that is already been unzipped need to be zipped named Lopyu_Stevany.zip and all of the folder need to be removed. </br>

We are using fork for this problem but it is not running as it should be. For the download,
```c
char *URL[] = {"wget", "--no-check-certificate", "https://drive.google.com/uc?id=1ZG8nRBRPquhYXq_sISdsVcXx5VdEgi-J&export=download", "/home/Sisop/Modul_2", "-q", NULL};
execv("/usr/bin/wget", URL);
```
The command to download the file is `wget` and make sure there is no certificate checking using `--no-check-certificate`. The third argument is the url of the file, the fourth argument is the path of the download, the fifth argument is `-q` to hide the download log that is happening in the terminal. After that, we need to execute the command using `execv`. </br>

The next step is to unzip the zip file.
```c
char *extract[] = {"unzip", "-q", "uc?id=1ZG8nRBRPquhYXq_sISdsVcXx5VdEgi-J&export=download", NULL};
execv("/usr/bin/unzip", extract);
```
The format is the same and the difference is only the command that is used which is `unzip`. </br>

From what we think of, in order to change the name of the folder, we can use `mv` command to its folder plus the new name.
```c
execl("/usr/bin/mv", "mv", "MUSIK", "Musyik", NULL);
```
The old name is MUSIK and the new name is Musyik.</br>
