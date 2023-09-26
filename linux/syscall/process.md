## 进程控制相关系统调用

#### 1、getpid

?> 获取进程 pid

#### 2、getppid

?> 获取父进程 pid

#### 3、getuid

```clike
uid_t getuid(void);
```

?> 获取进程的当前用户标识编号

#### 4、getgid

```clike
gid_t getgid(void);
```

?> 获取进程的当前用户组标识编号

#### 5、setuid

```clike
int setuid(uid_t uid);
```

?> 为进程设置一个有效的 uid

#### setgid

#### geteuid

#### getegid

#### setpgid

#### clone

#### fork

#### vfork

#### execve

#### exit

#### wait

#### kill

