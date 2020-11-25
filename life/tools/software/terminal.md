# Terminal

### Creates a symbolic link to the Home directory

Note: Symbolic links will be hidden

```bash
## Create symbolic link in Home directory
ln -s ~/Projects/git/mlcourse/ ~

## List all symbolic links
## Symbolic links will be listed with -> sign
ls -la
>> mlcourse -> /Users/andrewgurung/Projects/git/mlcourse/

## Navigate to Home directory
cd ~

## Navigate using symbolic link/shortcut
cd mlcourse
```

### Mount an external drive on MacOS

Step 1: Run the following command on Terminal

```bash
diskutil unmountDisk /dev/disk2
diskutil eject /dev/disk2
```

Step 2: Unplug and plug the external drive back to the computer.

