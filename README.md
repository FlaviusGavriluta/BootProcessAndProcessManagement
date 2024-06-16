# Boot Process and Process Management

## Story

You have access to your Linux VM through SSH, but what if something goes wrong and it doesn't want to boot? If this happens you want to be prepared!

## What are you going to learn?

- What are the stages of the boot process
- What is GRUB
- How to see running processes
- How to manage processes, what is PID and PPID
- How to run jobs in the background
- What is a subshell

## Tasks

1. Change the GRUB configuration for your 18.04 VirtualBox VM so you can actually see GRUB during the boot process.
    - When the VM is rebooted GRUB can be seen during the boot process.

2. Get a list of running processes and identify the process with PID equal to 1. Are there any processes with PPID equal to 1?
    - Process with PID and PPID equal to 1 identintified.

3. Practice process control skills.
    - Started a sleep process with the following command `sleep 600`.
    - Stopped the process without terminating it.
    - The process is restored to running state but this time in the background.
    - A list of background jobs is retrieved.
    - The background process is brought back to the foreground.
    - The process is terminated.

4. Execute commands in a subshell.
    - A command in a subshell is executed.
    - The PID and PPID of the subshell are identified.

## General requirements

None

## Hints

- Change `GRUB_TIMEOUT` from `0` to `10` and comment the line `GRUB_TIMEOUT_STYLE=hidden` in `/etc/default/grub`
- Changes in `/etc/default/grub` file can be applied with the command `sudo update-grub`
- Check the information in the file `/etc/default/grub` when you edit it. Note that this file is used to update /boot/grub/grub.cfg. You can examine this file too for better understanding of how GRUB is working.
- Check the background material "5 Keys You Can Press at the GRUB Menu" after you have completed the first task to learn more about what you can do on the GRUB Menu screen.
- Check the different options that you can use the command `ps` with. Use the man/info page `man ps` or `info ps`.
- Notice the difference between pressing `Ctrl + C` and `Ctrl + Z` for processes running in the foreground. Make us of the commands bg, fg, jobs.
- Use `&` at the end of a command to start it in the background. Use `ps faux` to list processes hierarchically.
- Run `echo "Hello from subshell $BASH_SUBSHELL to $(sleep 5; echo "John who is in subshell $BASH_SUBSHELL")."` and notice how the subshell delays the the output of the parent shell.
- You can run the same example as the previous hint but you can use a higher value for the `sleep` command so you can identify the PPID and PID of the bash shells with `ps`. Or you can use the environment variables `$BASHPID` and `$PPID`.

## Background materials

- <i class="far fa-exclamation"></i> [Linux startup process](https://en.wikipedia.org/wiki/Linux_startup_process)
- <i class="far fa-exclamation"></i> [Understanding the Boot process — BIOS vs UEFI](https://linuxhint.com/understanding_boot_process_bios_uefi)
- <i class="far fa-exclamation"></i> [GNU GRUB](https://en.wikipedia.org/wiki/GNU_GRUB)
- <i class="far fa-exclamation"></i> [5 Keys You Can Press at the GRUB Menu](https://www.omgubuntu.co.uk/2016/07/key-to-show-grub-menu-ubuntu)
- <i class="far fa-exclamation"></i> [Using ‘ps’ and ‘top’ To Monitor Linux Processes](http://www.linuxandubuntu.com/home/using-ps-and-top-to-monitor-linux-processes)
- <i class="far fa-exclamation"></i> [How to Run and Control Background Processes on Linux](https://www.howtogeek.com/440848/how-to-run-and-control-background-processes-on-linux/)
- <i class="far fa-exclamation"></i> [Linux Subshells for Beginners With Examples](https://linuxconfig.org/linux-subshells-for-beginners-with-examples)
