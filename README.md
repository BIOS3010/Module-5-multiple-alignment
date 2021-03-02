# Module-5-multiple-alignment
```bash
ssh [uio-username]@login.uio.no
```
where `[uio-username]` is your UiO-username.

```diff
! Can you recognize where you have logged in?
```diff

```bash
cd ~/Desktop
git clone XXXX
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
