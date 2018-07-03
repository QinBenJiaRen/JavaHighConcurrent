# JavaHighConcurrent
并行执行一些任务，可以使用ThreadPoolExecutor.
大部分的情况下直接使用ThreadPoolExecutor就可以满足要求，但是在某些场景下，比如瞬间大流量，为了提高响应和吞吐量，还是需要扩展一下
ThreadPoolExecutor.
ThreadPoolExecutor的执行流程：
`1.core线程还能应付到，则不断的创建新的线程
 2.core线程无法应付，则将任务扔到队列里面
 3.队列满了，则开始创建MAX线程，线程数达到MAX后，队列还一直是满的，则抛出RejectedExecutionException.
