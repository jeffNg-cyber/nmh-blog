---
layout: default
title: Finding/Searching files with locate, which, find 
---
# Locate
Search through database locate.db (Quick)
```
locate wget
```
Update database:
```
updatedb
```

# Which
Search through all $PATH (Slow)

```
which python
```

# Find

#### Name
```
find / -name regex* 2>/dev/null
```
#### Permission
```
find / -perm <PERM-Mode> 2>/dev/null
```
Permission mode prefix:
- No prefix: Exact match
- '-' prefix: At least the specified permission (or more) (AND conditions between user, group, everyone)
- '/' prefix: One of user, group, everyone satisfying is enough (OR conditions between user, group, everyone)

Special-bit Permission:
- 1000 - Sets the sticky bit
- 2000 - Sets the setgid bit
- 4000 - Sets the setuid bit

Others: 777, 766, 200, 300...

#### Executable, readable, writable
Files that is executable, directories that searchable by current user
```
find / -name regex* -executable 2>/dev/null
```
Files that is readable by current user
```
find / -name regex* -readable 2>/dev/null
```
Files that is writable by current user
```
find / -name regex* -writable 2>/dev/null
```