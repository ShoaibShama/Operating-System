# Operating-System
APPLICATION OF MULTITHREADING USING WEB SCRAPER AND ANALYSIS OF TIME TAKEN FOR DIFFERENT NUMBER OF THREADS
WEB SCRAPING

Web scraping, web harvesting, or web data extraction is data scraping used for extracting data from websites. The web scraping software may directly access the World Wide Web using the Hypertext Transfer Protocol or a web browser. While web scraping can be done manually by a software user, the term typically refers to automated processes implemented using a bot or web crawler. It is a form of copying in which specific data is gathered and copied from the web, typically into a central local database or spreadsheet, for later retrieval or analysis.

Web scraping a web page involves fetching it and extracting from it. Fetching is the downloading of a page (which a browser does when a user views a page).
Therefore, web crawling is a main component of web scraping, to fetch pages for later processing. Once fetched, then extraction can take place. The content of a page may be parsed, searched, reformatted, its data copied into a spreadsheet or loaded into a database. Web scrapers typically take something out of a page, to make use of it for another purpose somewhere else. An example would be to find and copy names and telephone numbers, or companies and their URLs, or
e-mail addresses to a list (contact scraping).

![image](https://user-images.githubusercontent.com/98227015/171368015-2363c023-1e11-4b9c-9f46-c6fd9dc6051d.png)



## WEB SCRAPER USING PYTHON

![image](https://user-images.githubusercontent.com/98227015/171368104-c97e9395-a4be-40fb-a3a9-7257dc589bd7.png)

Let’s say we wanted to download the images from an online photo gallery. It’s pretty easy to do this.

First, we need to get the URL from which the images are to be downloaded. Since there are a lot of images in a gallery per page, we only need a few pages to demonstrate the power of multithreading. Cv2 and urllib make extracting the URLs easy. Even though we’re only making 40 requests.

![image](https://user-images.githubusercontent.com/98227015/171368144-0d6eb75d-93e6-497f-9847-16d3a257b961.png)
 
### LIBRARIES USED:

![image](https://user-images.githubusercontent.com/98227015/171368199-5e1522ba-e362-4d38-8d58-3bbeafb61e53.png)


●	OpenCV-Python is a library of Python bindings designed to solve computer vision problems. cv2. imread() method loads an image from the specified file.
●	urllib is a Python module that can be used for opening URLs.
●	time is used for calculating time of process.

OUľPUľ:

![image](https://user-images.githubusercontent.com/98227015/171368251-baafd335-1950-4560-9711-0708524a49a3.png)

The files (40 in this case) are being downloaded one by one from a website and are saved in a directory on our system.
The time taken in this case was around 12 seconds. If the program is run for a relatively larger number of images, it will take much longer time.
This program can be completed in a much shorter time if we introduce multithreading in our code.
So, first let’s see what multithreading is.
 
##                                                          MULTITHREADING
In computer architecture, multithreading is the ability of a central processing unit (CPU) (or a single core in a multi-core processor) to provide multiple threads of execution concurrently, supported by the operating system. This approach differs from multiprocessing. In a multithreaded application, the threads share the resources of a single or multiple cores, which include the computing units, the CPU caches, and the translation lookaside buffer (TLB).
Where multiprocessing systems include multiple complete processing units in one or more cores, multithreading aims to increase utilization of a single core by using thread-level parallelism, as well as instruction-level parallelism. As the two techniques are complementary, they are combined in nearly all modern systems architectures with multiple multithreading CPUs and with CPUs with multiple multithreading cores.
The two main types of threads are user-level threads and kernel-level threads. A diagram that demonstrates these is as follows −

![image](https://user-images.githubusercontent.com/98227015/171368512-ea2f8d0f-ce5d-4283-9e3c-40a884e0c53b.png)
 
### User - Level Threads

The user-level threads are implemented by users and the kernel is not aware of the existence of these threads. It handles them as if they were single-threaded processes. User-level threads are small and much faster than kernel level threads. They are represented by a program counter (PC), stack, registers and a small process control block. Also, there is no kernel involvement in synchronization for user-level threads.
Advantages of User-Level Threads

Some of the advantages of user-level threads are as follows −

●	User-level threads are easier and faster to create than kernel-level threads. They can also be more easily managed.
●	User-level threads can be run on any operating system.
●	There are no kernel mode privileges required for thread switching in user-level threads.
Disadvantages of User-Level Threads

Some of the disadvantages of user-level threads are as follows −

●	Multithreaded applications in user-level threads cannot use multiprocessing to their advantage.
●	The entire process is blocked if one user-level thread performs blocking operation.

### Kernel-Level Threads

Kernel-level threads are handled by the operating system directly and the thread management is done by the kernel. The context information for the process as well as the process threads is all managed by the kernel. Because of this, kernel-level threads are slower than user-level threads.


Advantages of Kernel-Level Threads

Some	of	the	advantages	of	kernel-level	threads	are	as	follows	−
 
●	Multiple threads of the same process can be scheduled on different processors in kernel-level threads.
●	The kernel routines can also be multithreaded.
●	If a kernel-level thread is blocked, another thread of the same process can be scheduled by the kernel.

Disadvantages of Kernel-Level Threads

Some of the disadvantages of kernel-level threads are as follows −

●	A mode switch to kernel mode is required to transfer control from one thread to another in a process.
●	Kernel-level threads are slower to create as well as manage as compared to user-level threads.
-Advantages of multithreading
If a thread gets a lot of cache misses, the other threads can continue taking advantage of the unused computing resources, which may lead to faster overall execution, as these resources would have been idle if only a single thread were executed. Also, if a thread cannot use all the computing resources of the CPU (because instructions depend on each other's result), running another thread may prevent those resources from becoming idle.
-Disadvantages of multithreading
Multiple threads can interfere with each other when sharing hardware resources such as caches or translation lookaside buffers (TLBs). As a result, execution times of a single thread are not improved and can be degraded, even when only one thread is executing, due to lower frequencies or additional pipeline stages that are necessary to accommodate thread-switching hardware.
Overall efficiency varies; Intel claims up to 30% improvement with its
Hyper-Threading Technology, while a synthetic program just performing a loop of non-optimized dependent floating-point operations actually gains a 100% speed improvement when run in parallel. On the other hand, hand-tuned assembly language programs using MMX or AltiVec extensions and performing
 
data prefetches (as a good video encoder might) do not suffer from cache misses or idle computing resources. Such programs therefore do not benefit from hardware multithreading and can indeed see degraded performance due to contention for shared resources.
From the software standpoint, hardware support for multithreading is more visible to software, requiring more changes to both application programs and operating systems than multiprocessing. Hardware techniques used to support multithreading often parallel the software techniques used for computer multitasking. Thread scheduling is also a major problem in multithreading.

![image](https://user-images.githubusercontent.com/98227015/171368590-d8ec30c4-1593-4c2d-856c-7d49c4922fd6.png)

##                                          Multi-Threading Models in Process Management

Many operating systems support kernel thread and user thread in a combined way. Example of such system is Solaris. Multi-threading model are of three types.
1.	Many to many models.
2.	Many to one model
3.	one to one model.

### Many to Many Model
 
In this model, we have multiple user threads multiplexed to the same or lesser number of kernel level threads. Number of kernel level threads are specific to the machine; the advantage of this model is if a user thread is blocked, we can schedule others user
threads to another kernel thread. Thus, System doesn’t block if a particular thread is blocked.

![image](https://user-images.githubusercontent.com/98227015/171368677-4555c132-6730-4539-82df-265142d10322.png)

### Many to One Model

In this model, we have multiple user threads mapped to one kernel thread. In this model when a user thread makes a blocking system call entire process blocks. As we have only one kernel thread and only one user thread can access the kernel at a time, so multiple threads are not able access the multiprocessor at the same time.
 
 ![image](https://user-images.githubusercontent.com/98227015/171368718-7a24d464-c9ac-441a-8762-926b41ffd6ac.png)


### One to One Model

In this model, one to one relationship between kernel and user thread. In this model multiple threads can run on multiple processors. Problem with this model is that creating a user thread requires the corresponding kernel thread.

![image](https://user-images.githubusercontent.com/98227015/171368750-fa6618e2-fe16-4201-945b-e16ef968dc2c.png)

![image](https://user-images.githubusercontent.com/98227015/171368823-91c7a5ce-8c40-4e1c-b5af-67caebca3a71.png)

A Simple Example of Multithreading:
Let us try to understand the above code:
To import the threading module, we do:

import threading
To create a new thread, we create an object of Thread class. It takes following arguments:
target: the function to be executed by thread
args: the arguments to be passed to the target function
In above example, we created 2 threads with different target functions:

![image](https://user-images.githubusercontent.com/98227015/171368900-b5402a37-e7fe-415c-a596-de4c03652869.png)

![image](https://user-images.githubusercontent.com/98227015/171368932-2f6e188a-b121-4fbf-ae96-12cfa82c1bbd.png)



 
To start a thread, we use start method of Thread class.
Once the threads start, the current program (you can think of it like a main thread) also keeps on executing. In order to stop execution of current program
until a thread is complete, we use join method.

![image](https://user-images.githubusercontent.com/98227015/171368996-38b818df-0ee8-4952-b201-d15a140afa3b.png)

As a result, the current program will first wait for the completion of t1 and then t2. Once they are finished, the remaining statements of the current program are executed.

OUTPUT:
![image](https://user-images.githubusercontent.com/98227015/171369049-52958ad0-fc54-45f3-8855-51809b86533b.png)
 
##                                                     MULTITHREADED WEB SCRAPING

![image](https://user-images.githubusercontent.com/98227015/171369468-fd3b3010-365a-422f-b73e-26b823a8747d.png)


ľhe I/O tasks can be executed concuííently acíoss multiple thíeads in the same píocess, and that these tasks can happen while otheí Python bytecode is being inteípíeted.

Multithíeading with threading can give us a signiﬁcant boost heíe. We can take advantage of multithíeading by making a tiny change to ouí scíapeí


![image](https://user-images.githubusercontent.com/98227015/171369982-7d61514d-d712-4bb6-9e54-29ca103e2f3b.png)








Notice how little changed. Instead of looping through all the urls, we used multiple threads to execute the same program. Threading library is used to create multiple threads and hence, execute the function across many independent threads. The thread_count variable here is set to 8 and the number of images to 40. These threads operate asynchronously.

THE OUTPUT:
![image](https://user-images.githubusercontent.com/98227015/171370243-3cde8a1f-66ee-41a7-be0f-5816643c554d.png)


 
We see in the output, that ranges are set for 5 images each (8 threads and 40 images), and the images are not being downloaded in a serial manner.

![image](https://user-images.githubusercontent.com/98227015/171370284-a6c8c900-5485-4791-bf3a-a07476ea8ee7.png)

That’s all there is to it. Let’s see how big of an impact this tiny change can make. It took about 12 seconds to download the images before.


1.54 seconds for 40 images! That’s way faster. With so little in code changes, we got a roughly 8x speedup. At a larger scale, we’d likely see even more potential benefit from multithreading.
 
##                                                          IMPLEMENTATION

This multithreaded web scraper downloads given number of images from the url:


https://www.pokemon.com/us/pokedexWe have empty folders









### SIMPLE WEB SCRAPER (WITHOUT MULTITHREADING):
![image](https://user-images.githubusercontent.com/98227015/171370625-f850074b-85c7-4346-bc04-2e79d3a1b337.png)

![image](https://user-images.githubusercontent.com/98227015/171370684-fe600223-034a-4d5c-961e-069c212ec4cc.png)

### WEB SCRAPER WITH MULTITHREADING:

![image](https://user-images.githubusercontent.com/98227015/171370712-f0016b90-bbe5-4ea2-a1cc-5b042c575657.png)

 ![image](https://user-images.githubusercontent.com/98227015/171370735-1cbb8433-5000-4dd0-a304-8deddab7d836.png)
 
 ### THE IMAGES ARE STORED IN OUR FOLDERS
 
 ![image](https://user-images.githubusercontent.com/98227015/171370784-ee0d6f77-de9e-48eb-9500-5acddae43735.png)

 
### ANALYSIS OF TIME TAKEN FOR DIFFERENT NO. OF THREADS:
![image](https://user-images.githubusercontent.com/98227015/171370917-9436d6d4-8406-4cac-91b8-0a312b303412.png)
![image](https://user-images.githubusercontent.com/98227015/171370948-c7b7fc9e-29c8-457a-a735-b2d45f9f7ffa.png)



 
##                                                 APPLICATIONS OF WEB SCRAPING:
____________________________________________________________________________________________________________________
![image](https://user-images.githubusercontent.com/98227015/171370990-9325cafc-a6c4-4037-9fd0-4a8c249b8f28.png)


This is to say that the top applications of web scraping keeps on increasing as the web continues to expand, most of the applications of web scraping at the moment falls one of these:
●	E-commerce
●	Social Media
●	Sales Leads
●	Search Engine Optimization
●	Recruitment
●	Content production (Blogging, auto blogging, content curation and aggregation)




CONCLUSION
Basic web scrapping in Python is pretty easy, but it can be time consuming. Multiprocessing looks like the easiest solution if you Google things like “fast web scraping in python”, but it can only do so much.
Multithreading in web scraping can speed up web scraping just as easily and usually far more effectively
