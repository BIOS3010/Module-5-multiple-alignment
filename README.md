# Module 5 - Multiple sequence alignment
In these exercises, we will try out tools for multiple sequence alignment. Even though web-based systems exist, these tools are best run in the command line using our terminal application. If you have forgotten the basic bash commands, you should revisit the exercises from [Module 1](https://github.com/BIOS3010/Module-1-Unix-Python/blob/main/README.md)

We will focus on the T-Coffee multiple alignment tool, a widely used multiple-alignment tool. To install this, we will first have to learn how to log into an external server. 

## 5.1 Logging into the UiO-network and your home area using the terminal
You already have a "home space" on the UiO-network that you can access whenever you login with your username and password on a UiO-stationed PC, or when you use remote desktop login. Similarly, we can access your account also through the terminal using the `ssh` command:

```bash
ssh [uio-username]@login.uio.no
```
where `[uio-username]` is your UiO-username. 

**Note: you will be asked to type in your password. Type this in and press enter. But be aware that you will not see the characters being typed in to the terminal. This is for security reasons, such that people looking should not get information about how many characters your password consists of.**

```diff
! Execute the above command in your terminal, filling in your login details
! Can you recognize where you have logged in?
```

- Then, execute the following commands

```bash
cd ~/Desktop
mkdir Module5
cd Module5
```

```diff
! Explain the two commands above
! Can you recognize any files/folder?
```

## 5.2 Installing T-Coffee on your UiO home area
As we learned in [Module 1 (exercise 1.4.11)](https://github.com/BIOS3010/Module-1-Unix-Python/blob/main/exercises/Unix-2.md#1411-downloading-files-from-the-internet), we can download files from the internet using the `curl -O` command.

- Execute the following command to download the T-Coffee program:
```bash
curl -O http://tcoffee.org/Packages/Stable/Latest/T-COFFEE_installer_Version_13.45.0.4846264_linux_x64.tar.gz
```

```diff
! Decompress the file `T-COFFEE_installer_Version_13.45.0.4846264_linux_x64.tar.gz` (Hint: exercise 1.4.12)
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

Try to execute the the `t_coffee` program:
```bash
./t_coffee
```

If successful, there should be lots of options output to the screen


## 5.3 Performing multiple sequence alignments on globin sequences

### 5.3.1 Downloading files
Download these two files to the `Module6` folder you are currently in:

- https://raw.githubusercontent.com/BIOS3010/Module-4-Pairwise-alignment-2/main/beta_globin.fa
- https://raw.githubusercontent.com/BIOS3010/Module-4-Pairwise-alignment-2/main/divergent_globins.fa

```diff
! Inspect the content of the two files
! What does the two files contain
! What format are the two files in?
```
### 5.3.2 Performing multiple sequence alignments

To run T-Coffee, you should use the following command:

```bash
./t_coffee [sequencefile]
```
where `[sequencefile]` is a FASTA-file containing multiple sequenced that you want to align.

```diff
! Perform a multiple alignment on each of the files we downloaded in step 5.3.1
! What result files are generated?
```

### 5.3.3 Moving files from an external server to your own computer
The files produced by the T-Coffee program (`t_coffee`) are now placed inside the `Module6` folder on your UiO-Desktop. You could inspect these files visually using remote desktop, for example. However, there is a nice and easy way to transfer files from an external server to your own computer using the terminal command `scp`.

To do this:
- Copy the full path to the file (on the server) you want to transfer (Hint: use `pwd`)
- Open up a new Tab (or a new terminal) on your local computer, leaving the terminal window where you logged into your UiO-account open.
- Create a new folder called `Module-6` inside the `BIOS3010` folder in your home directory, and navigate into it
- In the new tab (or terminal window) type in: `scp [uio-username]@login.uio.no:[path-to-file] .
where `[uio-username]` is your UiO-username, and `[path-to-file]` is the path to the file you copied (just paste it in)
- Execute the command

```diff
! Perform the above steps on the files ending with .aln and .html (total 4 files)
! Verify that the four files are downloaded to the Module-6 folder on your computer
```

### 5.3.4 Initial inspection of the multiple sequence alignments
- Navigate to the two files `divergent_globins.html` and `beta_globin.html` on your computer using your normal, point-and-click way.
- Double-click on the two files to look at the results

```diff
! Inspect and describe the results of the two alignments
```

**TBD: Info on the sequences here!**

### 5.3.5 Using Jalview to inspec the alignments
In this exercise, we will use the Jalview program to look at the multiple sequence alignments.
- Download and install Jalview from here: http://www.jalview.org/getdown/release/
- Open Jalview
- Exit from the default sequences and structures displayed

- Choose `File` -> `Input alignment` -> `From file` and select the `beta_globin.aln` file

- Inpect the alignment
- Try out different coloring schemes by selecting these under the `Colour` tab


The coloring schemes are the following:
![colors](https://user-images.githubusercontent.com/5373069/109965215-f4706780-7cee-11eb-861d-1b91cb1ef78f.png)

Thus, using the `Hydrophobicity` coloring scheme, hydrophobic amino acids are colored red, and hydrophilic ones are colored blue. Similarly, the `Buried Index` colors buried amino acids in blue and exposed amino acids in green.

- Try to select individual sequences on the left. These can be moved around in the alignment using the arrow keys. Note what happens to the Quality scores in the bottom view.

- **Load the `divergent_globins.aln` alignment file and explore these also**
- What differences do you see between the alignments of the two different sets of globins?


- Spend 30+ minutes exploring the options in Jalview. Note in particular the functionality under `Calculate`->`Pairwise `
