# Module 5 - Multiple sequence alignment
In these exercises, we will try out tools for multiple sequence alignment. Even though web-based systems exist, these tools are best run in the command line using our terminal application. If you have forgotten the basic bash commands, you should revisit the exercises from [Module 1](https://github.com/BIOS3010/Module-1-Unix-Python/blob/main/README.md)

We will focus on the T-Coffee multiple alignment tool, a widely used multiple-alignment tool. To install this, we will first have to learn how to log into an external server. You already have a "home space" on the UiO-network that you can access whenever you login with your username and password on a UiO-stationed PC, or when you use remote desktop login. Similarly, we can access your account also through the terminal using the `ssh` command:

```bash
ssh [uio-username]@login.uio.no
```
where `[uio-username]` is your UiO-username. 



```diff
! Execute the above command in your terminal, filling in your login details
! Can you recognize where you have logged in?
```diff

- Then, execute the following commands

```bash
cd ~/Desktop
git clone XXXX
```

```diff
! Can you recognize any files/folder?
```

# Installing T-coffee
```bash
curl -O http://tcoffee.org/Packages/Stable/Latest/T-COFFEE_installer_Version_13.45.0.4846264_linux_x64.tar.gz
```

```diff
! Decompress the file `T-COFFEE_installer_Version_13.45.0.4846264_linux_x64.tar.gz`
! Hint: Look at exercise 1.4.12 from Module 1
! Navigate into the decompressed folder
! Which files and folders are inside `T-COFFEE_installer_Version_13.45.0.4846264_linux_x64`?
```

Then run these commands:
```bash
cp ./bin/t_coffee ../
cd ../
rm T-COFFEE_installer_Version_13.45.0.4846264_linux_x64.tar.gz
```

```diff
! Explain what happend in the three commands above
```

These files can be used to create alignments:

http://www.bioinfbook.org/wiley/3e/chapter6/WebDocument_6-01_5divergent_globins.htm
http://www.bioinfbook.org/wiley/3e/chapter6/WebDocument_6-02_5close_globins.htm

Running T-Coffee:
```bash
./t_coffee globin.fa
```


Visualizing in a visualizer
