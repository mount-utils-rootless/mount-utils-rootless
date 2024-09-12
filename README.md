# Termux Mount Utilities

## Overview

This package provides a suite of utilities for Termux to perform various file system operations such as mounting, unmounting, and mount-binding. It leverages tools like `genext2fs`, `proot`, `cmake`, `make`, `autoconf`, `clang`, and `debugfs` to enable these functionalities without requiring root access.

## Tools Included

- **genext2fs**: A tool to create ext2 file systems.
- **proot**: A user-space implementation of `chroot` with additional features.
- **cmake**: A cross-platform build-system generator.
- **make**: A build automation tool.
- **autoconf**: A tool for generating configuration scripts.
- **clang**: A compiler for C, C++, and other languages.
- **debugfs**: A file system debugger for ext2/ext3/ext4.

## Commands

### `mount`

This command mounts a file system image to a specified directory.

**Usage:**

```sh
mount --file <example.img> --mount <example.dir/mount>
```

**Parameters:**

- `--file <example.img>`: The path to the file system image to mount.
- `--mount <example.dir/mount>`: The directory where the file system image will be mounted.

**Example:**

```sh
mount --file /data/data/com.termux/files/home/example.img --mount /data/data/com.termux/files/home/mountpoint
```

### `unmount`

This command unmounts a previously mounted file system image.

**Usage:**

```sh
unmount --file <original.img> --umount <example.dir/mount>
```

**Parameters:**

- `--file <original.img>`: The path to the original file system image.
- `--umount <example.dir/mount>`: The directory where the file system image is mounted.

**Example:**

```sh
unmount --file /data/data/com.termux/files/home/example.img --umount /data/data/com.termux/files/home/mountpoint
```

### `mount-bind`

This command performs a bind mount, which allows you to mount a directory to another directory.

**Usage:**

```sh
mount-bind <dir/to/be/binded> <dir/to/bind/to>
```

**Parameters:**

- `<dir/to/be/binded>`: The directory you want to bind.
- `<dir/to/bind/to>`: The target directory where you want to bind the source directory.

**Example:**

```sh
mount-bind /data/data/com.termux/files/home/source_dir /data/data/com.termux/files/home/target_dir
```

## Installation
installation is as easiest as it can be we just have a .deb package in the releases tab that you can install in termux using dpkg -i *.deb
remember to do 
```bash
pkg update -y && pkg upgrade -y && pkg install clang make cmake git wget autoconf e2fsprogs
```
before installing the .deb package or it might ruin termux's packagement system
## Usage Examples

1. **Creating a File System Image:**

    ```sh
    genext2fs -b 1024 -i 256 -m 10 /data/data/com.termux/files/home/example.img
    ```

2. **Mounting the File System Image:**

    ```sh
    mount --file /data/data/com.termux/files/home/example.img --mount /data/data/com.termux/files/home/mountpoint
    ```

3. **Unmounting the File System Image:**

    ```sh
    unmount --file /data/data/com.termux/files/home/example.img --umount /data/data/com.termux/files/home/mountpoint
    ```

4. **Performing a Bind Mount:**

    ```sh
    mount-bind /data/data/com.termux/files/home/source_dir /data/data/com.termux/files/home/target_dir
    ```


## Contributing

If you find any issues or would like to contribute to this project, please fork the repository and submit a pull request.

## License

This package is distributed under the terms of the [MIT License](LICENSE).

## Contact

For any questions or support, please contact [me](mailto:momoszippy@gmail.com).
