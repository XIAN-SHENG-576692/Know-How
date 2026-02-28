#2026-02-19 16:21

1. check
	- 
    ```shell
    df -h
    ```
    ```shell
    lsblk
    ```
2. parted
	- 
    ```shell
    sudo parted <DISK>
    ```
    ```shell
    unit s
    ```
    ```shell
    print free
    ```
    ```shell
    resizepart
    ```
    ```shell
    quit
    ```
3. resize
	- 
    ```shell
    sudo resize2fs <Filesystem>
    ```
