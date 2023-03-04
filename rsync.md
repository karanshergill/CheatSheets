# RSYNC Utility
Used to synchronize files between a computer and a storage drive and across networked computers which provides fast incremental file transfer.

## Connecting to RSYNC
Generic Syntax
```
▶ rsync [OPTION] ... [USER@]HOST::SRC [DEST]

# [OPTION] : refers to the available options.
# [USER@] : optional parameter is used to access the the remote machine in an authenticated way. Omit for anonymous authentication.
# SRC : file or directory (or a list of multiple files and directories) to copy from.
# [DEST] : the file or directory to copy to, and square brackets indicate optional parameters.
```

## List all the available directories on the remote machine to an anonymous user
```
▶ rsync --list-only {target_IP}::

# --list-only : lists the files instead of copying them.
```

## List all the files in a share to an anonymous user
```
▶ rsync --list-only {target_IP}::{src_share_name}
```

## Copy files from remote machine to local machine
```
▶ rsync {target_IP}::{src_share_name/file_name.txt} {dest_file_name}
```
