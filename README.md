# pcleaner
Utility to clean ``lost`` processes.

In a similar way as you can use pgrep and pkill to look for and kill processes, this simple utility looks for processes matching the given filters and kills them.

This is quite useful in multi-user environments like the login nodes of a cluster where processes are left behind when the sessions are closed.

## Installation
Just deploy the script in one of the directories of your PATH.

## Usage
Look for processes older than 7 days
```
pcleaner --age $((24*7))
```

Only processes not owned by system uids (`uid < 1000`) are considered, you can change this using the `--min-uid` option.
```
pcleaner --age $((24*7)) --min-uid 2000
```

Look for and kill processes older than 7 days
```
pcleaner --age $((24*7)) --kill
```

Look for processes older than 7 days not belonging to user1 and user2:
```
pcleaner --age $((24*7)) --skip user1,user2
```

See all filter options:
```
pcleaner -h
```

