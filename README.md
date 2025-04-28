# csc415-assignment-6--file-system-solved
**TO GET THIS SOLUTION VISIT:** [CSC415 Assignment 6- File-System Solved](https://www.ankitcodinghub.com/product/csc415-assignment-6-file-system-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;56929&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;3&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (3 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSC415 Assignment 6- File-System Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (3 votes)    </div>
    </div>
Over the past moth you and your team have been designing components of a file system. You have defined the goals and designed the directory entry structure, the volume structure and the free space. You have written buffered read and write routines. Now it is time to implement your file system.

To help I have written the low level LBA based read and write. The routines are in fsLow.c, the necessary header for you to include file is fsLow.h. You do NOT need to understand the code in fsLow, but you do need to understand the header file and the functions. There are 4 key functions:

int startPartitionSystem (char * filename, uint64_t * volSize, uint64_t * blockSize);

startPartitionSystem – you specify a file name that is the “volume” of your hard drive. The volume size is rounded to even block size and is only used when creating the volume file. The block size must be a power of 2 (nominally 512 bytes).

On Return, the function will return 0 if success or a negative number if an error occurs. The values pointed to by volSize and blockSize are filled in with the values of the existing volume file.

int closePartitionSystem ();

closePartitionSystem – closes down the volume file and must be called prior to terminating the process, but no read or writes can happen after this call.

uint64_t LBAwrite (void * buffer, uint64_t lbaCount, uint64_t lbaPosition);

uint64_t LBAread (void * buffer, uint64_t lbaCount, uint64_t lbaPosition);

LBAread and LBAwrite take a buffer, a count of LBA blocks and the starting LBA block number (0 based). The buffer must be large enough for the number of blocks * the block size.

On return, these function returns the number of blocks read or written.

The source file fsLowDriver.c is a simple driver for the driver system and should not be part of your program.

In addition, I have written a hexdump utility that will allow you to analyze your volume file in the Hexdump subdirectory.

Your assignment is to write a file system!

You will need to format your volume, create and maintain a free space management system, initialize a root directory and maintain directory information, create, read, write, and delete files, and display info. See below for specifics.

I will provide an initial “main” that will be the driver to test you file system. Your group can modifiy this driver as needed. The driver will be interactive (with all built in commands) to list directories, create directories, add and remove files, copy files, move files, and two “special commands” one to copy from the normal filesystem to your filesystem and the other from your filesystem to the normal filesystem.

You should modify this driver as needed for your filesystem, adding the display/setting of any additional meta data, and other functions you want to add.

Some specifics – you need to provide the following interfaces:

int b_open (char * filename, int flags);

int b_read (int fd, char * buffer, int count);

int b_write (int fd, char * buffer, int count);

int b_seek (int fd, off_t offset, int whence);

void b_close (int fd);

Directory Functions – see https://www.thegeekstuff.com/2012/06/c-directory/ for reference.

int mfs_mkdir(const char *pathname, mode_t mode);

int mfs_rmdir(const char *pathname);

mfs_DIR * opendir(const char *name);

struct mfs_dirent *readdir(mfs_DIR *dirp);

int closedir(mfs_DIR *dirp);

char * mfs_getcwd(char *buf, size_t size);

char * mfs_setcwd(char *buf); //linux chdir

struct mfs_dirent

{

ino_t d_ino; /* inode number – not used by driver*/

off_t d_off; /* offset to the next dirent – not used by driver*/

unsigned short d_reclen; /* length of this record */

unsigned char d_type; /* type of file; not supported

by all file system types – not used by driver*/

char d_name[256]; /* filename */

};

Finally file stats – not all the fields in the structure are needed for this assingment

int mfs_stat(const char *path, struct mfs_stat *buf);

struct mfs_stat {

dev_t st_dev; /* ID of device containing file – not needed by driver*/

ino_t st_ino; /* inode number – not needed by driver program*/

mode_t st_mode; /* protection – not needed by driver program*/

nlink_t st_nlink; /* number of hard links – not needed by driver program*/

uid_t st_uid; /* user ID of owner – not needed by driver program*/

gid_t st_gid; /* group ID of owner – not needed by driver program*/

dev_t st_rdev; /* device ID (if special file) – not needed by driver program*/

off_t st_size; /* total size, in bytes */

blksize_t st_blksize; /* blocksize for file system I/O */

blkcnt_t st_blocks; /* number of 512B blocks allocated */

time_t st_atime; /* time of last access */

time_t st_mtime; /* time of last modification */

time_t st_ctime; /* time of last status change */

/* add additional attributes here for your file system */

};

These interfaces will also be provided to you in mfs.h along with the base driver (the base driver will be provided later).

Note: You will need to modify mfs.h for the mfs_DIR strucutre to be what your file system need to maintain and track.

This is deliberately vague, as it is dependent on your filesystem design. And this all you may get initially for a real-world assignment, so if you have questions, please ask.

We will discuss some of this in class.

For our purposes use 10,000,000 or less (minimum 500,000) bytes for the volume size and 512 bytes per sector. These are the values to pass into startPartitionSystem.

What needs to be submitted (via GitHub and iLearn):

All source files (.c and .h)

Modified Driver program (must be a program that just utilizes the header file for your file system).

The Driver program must be named: fsdriver.c

A make file (named “Makefile”) to build your entire program

&nbsp;
