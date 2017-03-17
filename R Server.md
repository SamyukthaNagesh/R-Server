# Contents
1. [R Server](#r-server)  
  1.1 [What is R Programming?](#what-is-r-programming)  
  1.2 [Benefits of R](#benefits-of-r)  
  1.3 [Limitations of R](#limitations-of-r)  
  1.4 [Microsoft R Family](#microsoft-r-family)  
  
# R Server
## What is R Programming?
R is an open source programming language that was built for statistical computing. It excels at data analysis, has built in graphics support, and it interacts well with tabular data structures.  

R is a tool of choice for data miners, data analysts, and data scientists. The rise of R has followed the rise of data science in enterprise; according to the TIOBE index, a measure of the popularity of programming languages, R has seen an explosion in usage since 2014. It is now one of the most popular programming languages in the world when it comes to data science and machine learning. 

[insert image ref here]

## Benefits of R
+ **Dataset friendly**  

  One of R’s greatest strengths is that it greatly improves efficiency and development time, as you do not have to formulate loops as often as in other programming languages. You can call a mean() or a sum function, for example, on the entirety of a column of a dataset without having to build a nested loop.
+ **Easy to learn**  

  R feels very natural for someone used to Excel or SQL, as it treats data as rows and columns rather than individual variables or data structures to be looped over. Being a higher-level programming language like Python or JavaScript, R is also easy to pick up, with many of the more mundane tasks being abstracted away, like garbage collection, variable typing, formulating many loops, or handling many exemptions. 
+ **Large community**  
  
  For an open source technology to become useful, it must have a large community that helps improve and make the technology better. R has gained enough of a following to receive a critical mass for an open source technology. Thus, practitioners of R will have the benefit a well-hydrated support community such as StackOverflow and other public forums. R also has more than ten thousand free and open source packages on [CRAN](https://cran.r-project.org/), the community that curates and distributes R packages. The number of R packages on CRAN have risen exponentially over the years.  
  
  [insert image ref here]

## Limitations of R
As much of a force and a movement that open source R has been, the programming language itself lacks the power and efficiency of other languages. R has always had constraints around scaling out to big data. The four biggest constraints of R are listed below:

1. **Single Core:** R only runs on a single core. Normally computer programs that utilize other languages can break a task into chunks and have it be executed on parallel on another core, greatly speeding up the operation or computation. For example, if you had to traverse 200 decision trees of a decision forest model, and you had four cores, each core would split the load of all the trees and the job would run 4 times faster. With R, each of the 200 trees would take their turn sequentially through a single core, ignoring any cores that may wish to help. As data grows in width and length, this parallel execution present with multiple cores is crucial to creating models in a timely manner. It also makes it so open source R cannot be utilized during a high-performance compute instance, or in a simple use case where you may just wish to rent a 32-core virtual machine from the cloud to speed up the job --- 31 of those cores would be useless to R.  

2. **Sequential Processing:** Even within a single core, a computation can be parallelized by utilizing multiple threads. R, however, must process everything sequentially -- a single thread, within a single core.  

3. **In-memory Compute:** R must see the entirety of a file and have it be read into memory (RAM) for it to be processed. It lacks the ability to process things as a stream of a file. What this means is that you are severely bottlenecked by the size of how much memory you have on your machine. On top of this, the R data frame can bloat up files by 3 times. So, users with 8 GBs of ram can only hope to work on files around 1.4 GB in size. Users can avoid this issue by renting a machine with much larger memory, but even that solution has its limits since the VM with the largest RAM that one can currently rent from Azure has 448 GB of RAM -- hardly practical for big data scenarios.  

4. **Cannot Be Distributed:** R cannot even be distributed within a single computer, let alone across multiple computers. However, the current trend in solving big data is not to “scale up” but to “scale wide”: you must use distributed computing frameworks like Hadoop or Spark, where you get a cluster of computers to parallelize a task because the task or data has outstripped the resources of a single machine.  

What happens when you expand beyond a couple of gigabytes of data? Traditionally, you would pack up your data and use something else; Python, Java, or Mahout, to name a few options. Not anymore --- now it’s possible to stick with R throughout your production analysis all the way to deployment, regardless of the data size, even in a distributed Hadoop or Spark environment. Introducing: *Microsoft R Server.*

## Microsoft R Family
Microsoft offers four product lines to support R by unlocking its limits and increasing its scope: SQL Server R, Microsoft R Server, Microsoft R, and Microsoft R Open.  

[insert image ref here]  

Microsoft R Server delivers enterprise-class performance and scalability for your R-based applications, with libraries that allow you to write once and deploy across multiple platforms, all with minimal effort --- whether on-premises, or in the cloud.
By using and extending open source R, Microsoft R Server is fully compatible with R scripts, functions and CRAN packages, using them to analyze data at an enterprise scale. It also addresses the in-memory limitations of open source R by adding parallel and chunked processing of data in Microsoft R Server, enabling users to run analytics on data much bigger than what fits in main memory. And since R Server is built on top of Microsoft R Open, you can use any open source R packages to build your analytics.
