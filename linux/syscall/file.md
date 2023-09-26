## 文件相关调用

#### 1、open

?> 打开或创建文件

#### 2、openat

?> 在指定目录 fd 下创建文件

#### 3、creat

?> 创建文件，现在很少使用了，可以使用 open 代替

#### 4、close

?> 关闭打开的文件描述符

#### 5、stat

```clike
int stat(const char *restrict pathname, struct stat *restrict statbuf);
```

?> 查询文件状态, 这里使用文件路径作为参数

#### 6、fstat

```clike
int fstat(int fd, struct stat *statbuf);
```

?> 查询文件状态, 这里使用文件描述符 fd 作为参数

#### 7、lstat

```clike
int lstat(const char *restrict pathname, struct stat *restrict statbuf);
```

?> 查询软连接文件状态, 这里使用文件路径作为参数

#### 8、access

?> 判断某个文件是否存在，或者有相关的访问权限

#### 9、dup

?> 拷贝文件描述符， 并返回复制后的值

#### 10、dup2

?> 拷贝文件描述符， 并可以指定 `newfd` 的值，如果 `newfd` 已经存在，则会先 `close`，则拷贝

#### 11、dup3

?> 拷贝文件描述符， 并可以指定值 `newfd` 的值， 以及 flags

#### 12、fcntl

?> 文件控制，相比之下 `ioctl` 会更灵活

#### 13、flock

?> 对文件锁的添加与访问

#### 14、fsync

?> 文件数据同步

#### 15、fdatasync

?> 文件数据同步， 这里特指仅同步数据，而不同步文件更新时间

#### 16、truncate

```clike
int truncate(const char *path, off_t length);
```

?> 文件截断/设置文件长度（length），如果 `length` 比原有文件长，则会对剩余部分补零或者使用空洞，如果比原有文件短，超出的部分则会被丢弃。

#### 17、ftruncate

?> 同上，设置文件长度（length）

#### 18、fallocate

?> 不可扩展的，linux 专用的系统调用；fallocate用于将块预分配给文件。对于支持`fallocate`系统调用的文件系统，这可以通过分配块并将其标记为未初始化来快速完成，因此不需要对数据块进行I / O操作。这是创建文件而不是用零填充的更快的方法。大文件几乎可以立即创建，而不必等待任何I / O操作完成。在以下文件系统上支持fallocate系统调用：btrfs，ext4，ocfs2和xfs文件系统

#### 19、link

```clike
int link(const char *oldpath, const char *newpath);
```

?> 创建文件硬链接（文件别名）。

#### 20、unlink

?> 删除文件硬链接
