listing 1
// A simple semaphore example. 
 
import java.util.concurrent.*; 
 
class SemDemo { 
 
  public static void main(String args[]) { 
    Semaphore sem = new Semaphore(1); 
 
    new IncThread(sem, "A"); 
    new DecThread(sem, "B"); 
 
  } 
} 
 
// A shared resource. 
class Shared { 
  static int count = 0; 
} 
 
// A thread of execution that increments count. 
class IncThread implements Runnable { 
  String name; 
  Semaphore sem; 
 
  IncThread(Semaphore s, String n) { 
    sem = s; 
    name = n; 
    new Thread(this).start(); 
  } 
 
  public void run() { 
     
    System.out.println("Starting " + name); 
 
    try { 
      // First, get a permit. 
      System.out.println(name + " is waiting for a permit."); 
      sem.acquire(); 
      System.out.println(name + " gets a permit."); 
 
      // Now, access shared resource. 
      for(int i=0; i < 5; i++) { 
        Shared.count++; 
        System.out.println(name + ": " + Shared.count); 
 
        // Now, allow a context switch -- if possible. 
        Thread.sleep(10); 
      } 
    } catch (InterruptedException exc) { 
      System.out.println(exc); 
    } 
 
    // Release the permit. 
    System.out.println(name + " releases the permit."); 
    sem.release(); 
  } 
} 
 
// A thread of execution that deccrements count. 
class DecThread implements Runnable { 
  String name; 
  Semaphore sem; 
 
  DecThread(Semaphore s, String n) { 
    sem = s; 
    name = n; 
    new Thread(this).start(); 
  } 
 
  public void run() { 
     
    System.out.println("Starting " + name); 
 
    try { 
      // First, get a permit. 
      System.out.println(name + " is waiting for a permit."); 
      sem.acquire(); 
      System.out.println(name + " gets a permit."); 
 
      // Now, access shared resource. 
      for(int i=0; i < 5; i++) { 
        Shared.count--; 
        System.out.println(name + ": " + Shared.count); 
 
        // Now, allow a context switch -- if possible. 
        Thread.sleep(10); 
      } 
    } catch (InterruptedException exc) { 
      System.out.println(exc); 
    } 
 
    // Release the permit. 
    System.out.println(name + " releases the permit."); 
    sem.release(); 
  } 
}

listing 2
// An implementation of a producer and consumer 
// that use semaphores to control synchronization. 
 
import java.util.concurrent.Semaphore; 
 
class Q { 
  int n; 
 
  // Start with consumer semaphore unavailable. 
  static Semaphore semCon = new Semaphore(0); 
  static Semaphore semProd = new Semaphore(1); 
 
  void get() { 
    try { 
      semCon.acquire(); 
    } catch(InterruptedException e) { 
      System.out.println("InterruptedException caught"); 
    } 
 
     System.out.println("Got: " + n); 
     semProd.release(); 
  } 
 
  void put(int n) { 
    try { 
      semProd.acquire(); 
    } catch(InterruptedException e) { 
      System.out.println("InterruptedException caught"); 
    } 
 
    this.n = n; 
    System.out.println("Put: " + n); 
    semCon.release(); 
  } 
} 
 
class Producer implements Runnable { 
  Q q; 
 
  Producer(Q q) { 
    this.q = q; 
    new Thread(this, "Producer").start(); 
  } 
 
  public void run() { 
    for(int i=0; i < 20; i++) q.put(i); 
  } 
} 
 
class Consumer implements Runnable { 
  Q q; 
 
  Consumer(Q q) { 
    this.q = q; 
    new Thread(this, "Consumer").start(); 
  } 
 
  public void run() { 
    for(int i=0; i < 20; i++)  q.get(); 
  } 
} 
 
class ProdCon { 
  public static void main(String args[]) { 
    Q q = new Q(); 
    new Consumer(q); 
    new Producer(q); 
  } 
}

listing 3
// An example of CountDownLatch. 
 
import java.util.concurrent.CountDownLatch; 
 
class CDLDemo { 
  public static void main(String args[]) { 
    CountDownLatch cdl = new CountDownLatch(5); 
 
    System.out.println("Starting"); 
 
    new MyThread(cdl); 
 
    try { 
      cdl.await(); 
    } catch (InterruptedException exc) { 
      System.out.println(exc); 
    } 
 
    System.out.println("Done"); 
  } 
} 
 
class MyThread implements Runnable { 
  CountDownLatch latch; 
 
  MyThread(CountDownLatch c) { 
    latch = c; 
    new Thread(this).start(); 
  } 
 
  public void run() { 
    for(int i = 0; i<5; i++) { 
      System.out.println(i); 
      latch.countDown(); // decrement count 
    } 
  } 
}

listing 4
// An example of CyclicBarrier. 
 
import java.util.concurrent.*; 
 
class BarDemo { 
  public static void main(String args[]) { 
    CyclicBarrier cb = new CyclicBarrier(3, new BarAction() ); 
 
    System.out.println("Starting"); 
 
    new MyThread(cb, "A"); 
    new MyThread(cb, "B"); 
    new MyThread(cb, "C"); 
 
  } 
} 
 
// A thread of execution that uses a CyclicBarrier. 
class MyThread implements Runnable { 
  CyclicBarrier cbar; 
  String name; 
 
  MyThread(CyclicBarrier c, String n) { 
    cbar = c; 
    name = n; 
    new Thread(this).start(); 
  } 
 
  public void run() { 
     
    System.out.println(name); 
 
    try { 
      cbar.await(); 
    } catch (BrokenBarrierException exc) { 
      System.out.println(exc); 
    } catch (InterruptedException exc) { 
      System.out.println(exc); 
    } 
  } 
} 
 
// An object of this class is called when the  
// CyclicBarrier ends. 
class BarAction implements Runnable { 
  public void run() { 
    System.out.println("Barrier Reached!"); 
  } 
}

listing 5
// An example of Exchanger. 
 
import java.util.concurrent.Exchanger; 
 
class ExgrDemo { 
  public static void main(String args[]) { 
    Exchanger<String> exgr = new Exchanger<String>(); 
 
    new UseString(exgr); 
    new MakeString(exgr); 
  } 
} 
 
// A Thread that constructs a string. 
class MakeString implements Runnable { 
  Exchanger<String> ex; 
  String str; 
 
  MakeString(Exchanger<String> c) { 
    ex = c; 
    str = new String(); 
 
    new Thread(this).start(); 
  } 
 
  public void run() { 
    char ch = 'A'; 
 
    for(int i = 0; i < 3; i++) { 
 
      // Fill Buffer 
      for(int j = 0; j < 5; j++) 
        str += ch++; 
 
      try { 
        // Exchange a full buffer for an empty one. 
        str = ex.exchange(str); 
      } catch(InterruptedException exc) { 
        System.out.println(exc); 
      } 
    }         
  } 
} 
 
// A Thread that uses a a string. 
class UseString implements Runnable { 
  Exchanger<String> ex; 
  String str; 
 
  UseString(Exchanger<String> c) { 
    ex = c; 
    new Thread(this).start(); 
  } 
 
  public void run() { 
 
    for(int i=0; i < 3; i++) {       
      try { 
        // Exchange an empty buffer for a full one. 
        str = ex.exchange(new String()); 
        System.out.println("Got: " + str); 
      } catch(InterruptedException exc) { 
        System.out.println(exc); 
      } 
    }    
  } 
}

listing 6
// An example of Phaser. 
  
import java.util.concurrent.*;  
  
class PhaserDemo {  
  public static void main(String args[]) {  
    Phaser phsr = new Phaser(1);  
    int curPhase; 
  
    System.out.println("Starting");  
  
    new MyThread(phsr, "A");  
    new MyThread(phsr, "B");  
    new MyThread(phsr, "C");  
 
    // Wait for all threads to complete phase one. 
    curPhase = phsr.getPhase(); 
    phsr.arriveAndAwaitAdvance(); 
    System.out.println("Phase " + curPhase + " Complete"); 
 
    // Wait for all threads to complete phase two. 
    curPhase =  phsr.getPhase(); 
    phsr.arriveAndAwaitAdvance(); 
    System.out.println("Phase " + curPhase + " Complete"); 
 
    curPhase =  phsr.getPhase(); 
    phsr.arriveAndAwaitAdvance(); 
    System.out.println("Phase " + curPhase + " Complete"); 
 
    // Deregister the main thread. 
    phsr.arriveAndDeregister(); 
 
    if(phsr.isTerminated()) 
      System.out.println("The Phaser is terminated"); 
  }  
}  
  
// A thread of execution that uses a Phaser.  
class MyThread implements Runnable {  
  Phaser phsr;  
  String name;  
  
  MyThread(Phaser p, String n) {  
    phsr = p;  
    name = n;  
    phsr.register(); 
    new Thread(this).start();  
  }  
  
  public void run() {  
      
    System.out.println("Thread " + name + " Beginning Phase One");  
    phsr.arriveAndAwaitAdvance(); // Signal arrival. 
 
    // Pause a bit to prevent jumbled output. This is for illustration  
    // only. It is not required for the proper opration of the phaser. 
    try { 
      Thread.sleep(10); 
    } catch(InterruptedException e) { 
      System.out.println(e); 
    } 
 
    System.out.println("Thread " + name + " Beginning Phase Two");  
    phsr.arriveAndAwaitAdvance(); // Signal arrival. 
 
    // Pause a bit to prevent jumbled output. This is for illustration  
    // only. It is not required for the proper opration of the phaser. 
    try { 
      Thread.sleep(10); 
    } catch(InterruptedException e) { 
      System.out.println(e); 
    } 
 
    System.out.println("Thread " + name + " Beginning Phase Three");  
    phsr.arriveAndDeregister(); // Signal arrival and deregister. 
  }  
}

listing 7
// Extend Phaser and override onAdvance() so that only a specific 
// number of phases are executed. 
  
import java.util.concurrent.*;  
 
// Extend MyPhaser to allow only a specific number of phases 
// to be executed. 
class MyPhaser extends Phaser { 
  int numPhases; 
 
  MyPhaser(int parties, int phaseCount) { 
    super(parties); 
    numPhases = phaseCount - 1; 
  } 
 
  // Override onAdvance() to execute the specified  
  // number of phases. 
  protected boolean onAdvance(int p, int regParties) { 
    // This println() statement is for illustration only. 
    // Normally, onAdvance() will not display output. 
    System.out.println("Phase " + p + " completed.\n"); 
 
    // If all phases have completed, return true 
    if(p == numPhases || regParties == 0) return true; 
 
    // Otherwise, return false. 
    return false;  
  } 
} 
 
class PhaserDemo2 {  
  public static void main(String args[]) {  
  
    MyPhaser phsr = new MyPhaser(1, 4); 
  
    System.out.println("Starting\n");  
  
    new MyThread(phsr, "A");  
    new MyThread(phsr, "B");  
    new MyThread(phsr, "C");  
 
    // Wait for the specified number of phases to complete.. 
    while(!phsr.isTerminated()) { 
      phsr.arriveAndAwaitAdvance(); 
    } 
 
    System.out.println("The Phaser is terminated"); 
  }  
}  
  
// A thread of execution that uses a Phaser.  
class MyThread implements Runnable {  
  Phaser phsr;  
  String name;  
  
  MyThread(Phaser p, String n) {  
    phsr = p;  
    name = n;  
    phsr.register(); 
    new Thread(this).start();  
  }  
  
  public void run() {  
  
    while(!phsr.isTerminated()) {      
      System.out.println("Thread " + name + " Beginning Phase " + 
                         phsr.getPhase());  
 
      phsr.arriveAndAwaitAdvance();  
 
      // Pause a bit to prevent jumbled output. This is for illustration  
      // only. It is not required for the proper opration of the phaser. 
      try { 
        Thread.sleep(10); 
      } catch(InterruptedException e) { 
        System.out.println(e); 
      } 
    } 
 
  }  
}

listing 8
// A simple example that uses an Executor. 
 
import java.util.concurrent.*; 
 
class SimpExec { 
  public static void main(String args[]) { 
    CountDownLatch cdl = new CountDownLatch(5); 
    CountDownLatch cdl2 = new CountDownLatch(5); 
    CountDownLatch cdl3 = new CountDownLatch(5); 
    CountDownLatch cdl4 = new CountDownLatch(5); 
    ExecutorService es = Executors.newFixedThreadPool(2); 
 
    System.out.println("Starting"); 
 
    // Start the threads. 
    es.execute(new MyThread(cdl, "A")); 
    es.execute(new MyThread(cdl2, "B")); 
    es.execute(new MyThread(cdl3, "C")); 
    es.execute(new MyThread(cdl4, "D")); 
 
    try { 
      cdl.await(); 
      cdl2.await(); 
      cdl3.await(); 
      cdl4.await(); 
    } catch (InterruptedException exc) { 
      System.out.println(exc); 
    } 
 
    es.shutdown(); 
    System.out.println("Done"); 
  } 
} 
 
class MyThread implements Runnable { 
  String name; 
  CountDownLatch latch; 
 
  MyThread(CountDownLatch c, String n) { 
    latch = c; 
    name = n; 
 
    new Thread(this); 
  } 
 
  public void run() { 
     
    for(int i = 0; i < 5; i++) { 
      System.out.println(name + ": " + i); 
      latch.countDown(); 
    } 
  } 
}

listing 9
// An example that uses a Callable. 
 
import java.util.concurrent.*; 
 
class CallableDemo { 
  public static void main(String args[]) { 
    ExecutorService es = Executors.newFixedThreadPool(3); 
    Future<Integer> f; 
    Future<Double> f2; 
    Future<Integer> f3; 
 
    System.out.println("Starting"); 
 
    f = es.submit(new Sum(10)); 
    f2 = es.submit(new Hypot(3, 4)); 
    f3 = es.submit(new Factorial(5)); 
 
    try { 
      System.out.println(f.get()); 
      System.out.println(f2.get()); 
      System.out.println(f3.get()); 
    } catch (InterruptedException exc) { 
      System.out.println(exc); 
    } 
    catch (ExecutionException exc) { 
      System.out.println(exc); 
    } 
 
    es.shutdown(); 
    System.out.println("Done"); 
  } 
} 
 
// Following are three computational threads. 
 
class Sum implements Callable<Integer> {  
  int stop; 
 
  Sum(int v) { stop = v; } 
 
  public Integer call() {  
    int sum = 0; 
    for(int i = 1; i <= stop; i++) { 
      sum += i; 
    } 
    return sum; 
  } 
} 
    
class Hypot implements Callable<Double> {  
  double side1, side2; 
 
  Hypot(double s1, double s2) { 
    side1 = s1; 
    side2 = s2; 
  } 
    
  public Double call() {  
    return Math.sqrt((side1*side1) + (side2*side2)); 
  } 
} 
    
 
class Factorial implements Callable<Integer> {  
  int stop; 
 
  Factorial(int v) { stop = v; } 
 
  public Integer call() {  
    int fact = 1; 
    for(int i = 2; i <= stop; i++) { 
      fact *= i; 
    } 
    return fact; 
  } 
}

listing 10
// A simple lock example. 
 
import java.util.concurrent.locks.*; 
 
class LockDemo { 
 
  public static void main(String args[]) { 
    ReentrantLock lock = new ReentrantLock(); 
 
    new LockThread(lock, "A"); 
    new LockThread(lock, "B"); 
 
  } 
} 
 
// A shared resource. 
class Shared { 
  static int count = 0; 
} 
 
// A thread of execution that increments count. 
class LockThread implements Runnable { 
  String name; 
  ReentrantLock lock; 
 
  LockThread(ReentrantLock lk, String n) { 
    lock = lk; 
    name = n; 
    new Thread(this).start(); 
  } 
 
  public void run() { 
     
    System.out.println("Starting " + name); 
 
    try { 
      // First, lock count. 
      System.out.println(name + " is waiting to lock count."); 
      lock.lock(); 
      System.out.println(name + " is locking count."); 
 
      Shared.count++; 
      System.out.println(name + ": " + Shared.count); 
 
      // Now, allow a context switch -- if possible. 
      System.out.println(name + " is sleeping."); 
      Thread.sleep(1000); 
    } catch (InterruptedException exc) { 
      System.out.println(exc); 
    } finally { 
      // Unlock 
      System.out.println(name + " is unlocking count."); 
      lock.unlock(); 
    } 
  } 
}

listing 11
// A simple example of Atomic. 
 
import java.util.concurrent.atomic.*; 
 
class AtomicDemo { 
 
  public static void main(String args[]) { 
    new AtomThread("A"); 
    new AtomThread("B"); 
    new AtomThread("C"); 
  } 
} 
 
class Shared { 
  static AtomicInteger ai = new AtomicInteger(0); 
} 
 
// A thread of execution that increments count. 
class AtomThread implements Runnable { 
  String name; 
 
  AtomThread(String n) { 
    name = n; 
    new Thread(this).start(); 
  } 
 
  public void run() { 
     
    System.out.println("Starting " + name); 
 
    for(int i=1; i <= 3; i++) 
      System.out.println(name + " got: " +  
             Shared.ai.getAndSet(i)); 
  } 
}

listing 12
// A simple example of the basic divide-and-conquer strategy. 
// In this case, RecursiveAction is used. 
import java.util.concurrent.*;  
import java.util.*; 
 
// A ForkJoinTask (via RecursiveAction) that transforms 
// the elements in an array of doubles into their square roots. 
class SqrtTransform extends RecursiveAction { 
  // The threshold value is arbitrarily set at 1,000 in this example. 
  // In real world code, its optimal value can be determined by 
  // profiling and experimentation.  
  final int seqThreshold = 1000; 
 
  // Array to be accessed. 
  double[] data;  
 
  // Deterines what part of data to process. 
  int start, end; 
 
  SqrtTransform(double[] vals, int s, int e ) { 
    data = vals; 
    start = s; 
    end = e; 
  } 
 
  // This is the method in which parallel computation will occur. 
  protected void compute() { 
 
    // If number of elements is below the sequential threshold, 
    // then process sequentially. 
    if((end - start) < seqThreshold) { 
      // Transform each element into its square root. 
      for(int i = start; i < end; i++) { 
         data[i] = Math.sqrt(data[i]); 
      } 
    } 
    else { 
      // Otherwise, continue to break the data into smaller peices. 
 
      // Find the midpoint. 
      int middle = (start + end) / 2; 
 
      // Invoke new tasks, using the subdivided data. 
      invokeAll(new SqrtTransform(data, start, middle), 
                new SqrtTransform(data, middle, end)); 
    } 
  } 
} 
 
// Demonstrate parallel execution.  
class ForkJoinDemo {  
  public static void main(String args[]) {  
    // Create a task pool. 
    ForkJoinPool fjp = new ForkJoinPool(); 
 
    double[] nums = new double[100000]; 
 
    // Give nums some values. 
    for(int i = 0; i < nums.length; i++) 
      nums[i] = (double) i; 
 
    System.out.println("A portion of the original sequence:"); 
     
    for(int i=0; i < 10; i++)  
      System.out.print(nums[i] + " ");  
    System.out.println("\n"); 
 
    SqrtTransform task = new SqrtTransform(nums, 0, nums.length); 
 
    // Start the main ForkJoinTask. 
    fjp.invoke(task); 
 
    System.out.println("A portion of the transformed sequence" + 
                       " (to four decimal places):"); 
    for(int i=0; i < 10; i++) 
      System.out.format("%.4f ", nums[i]); 
    System.out.println(); 
  }  
}

listing 13
// A simple program that lets you experiment with the effects of 
// changing the threshold and parallelism of a ForkJoinTak. 
import java.util.concurrent.*;  
 
// A ForkJoinTask (via RecursiveAction) that performs a 
// a transform on the elements of an array of doubles. 
class Transform extends RecursiveAction { 
 
  // Sequential threshold, which is set by the construtor. 
  int seqThreshold; 
 
  // Array to be accessed. 
  double[] data; 
 
  // Deterines what part of data to process. 
  int start, end; 
 
  Transform(double[] vals, int s, int e, int t ) { 
    data = vals; 
    start = s; 
    end = e; 
    seqThreshold = t; 
  } 
 
  // This is the method in which parralell computation will occur. 
  protected void compute() { 
 
    // If number of elements is below the sequential threshold, 
    // then process sequentially. 
    if((end - start) < seqThreshold) { 
      // The following code assigns an element at even an index the 
      // square root of its original value. An elements at an odd 
      // index is assigned its cube root. This code is designed 
      // to simply consume CPU time so that the effects of concurrent 
      // execution are more readily observable. 
      for(int i = start; i < end; i++) { 
        if((data[i] % 2) == 0) 
          data[i] = Math.sqrt(data[i]); 
        else  
          data[i] = Math.cbrt(data[i]); 
      } 
    } 
    else { 
      // Otherwise, continue to break the data into smaller peices. 
 
      // Find the midpoint. 
      int middle = (start + end) / 2; 
 
      // Invoke new tasks, using the subdivided data. 
      invokeAll(new Transform(data, start, middle, seqThreshold), 
                new Transform(data, middle, end, seqThreshold)); 
    } 
  } 
} 
 
// Demonstrate parallel execution.  
class FJExperiment {  
 
  public static void main(String args[]) {  
    int pLevel; 
    int threshold; 
 
    if(args.length !=  2) { 
      System.out.println("Usage: FJExperiment threshold parallism"); 
      return; 
    } 
 
    pLevel = Integer.parseInt(args[0]); 
    threshold = Integer.parseInt(args[1]);   
 
    // These variables are used to time the task. 
    long beginT, endT; 
 
    // Create a task pool.  Notice that the parallelsim level is set. 
    ForkJoinPool fjp = new ForkJoinPool(pLevel); 
 
    double[] nums = new double[1000000]; 
 
    for(int i = 0; i < nums.length; i++) 
      nums[i] = (double) i; 
 
    Transform task = new Transform(nums, 0, nums.length, threshold); 
 
    // Starting timing. 
    beginT = System.nanoTime(); 
 
    // Start the main ForkJoinTask. 
    fjp.invoke(task); 
 
    // End timing. 
    endT = System.nanoTime(); 
 
    System.out.println("Level of parallelism: " + pLevel); 
    System.out.println("Sequential threshold: " + threshold); 
    System.out.println("Elapsed time: " + (endT - beginT) + " ns"); 
    System.out.println(); 
  }  
}

listing 14
// A simple example that uses RecursiveTask<V>. 
import java.util.concurrent.*;  
 
// A RecursiveTask that computes the summation of an array of doubles. 
class Sum extends RecursiveTask<Double> { 
 
  // The sequential threshold value.  
  final int seqThresHold = 500; 
 
  // Array to be accessed. 
  double[] data;  
 
  // Deterines what part of data to process. 
  int start, end; 
 
  Sum(double[] vals, int s, int e ) { 
    data = vals; 
    start = s; 
    end = e; 
  } 
 
  // Find the summation of an array of doubles. 
  protected Double compute() { 
    double sum = 0; 
 
    // If number of elements is below the sequential threshold, 
    // then process sequentially. 
    if((end - start) < seqThresHold) { 
      // Sum the elements. 
      for(int i = start; i < end; i++) sum += data[i]; 
    } 
    else { 
      // Otherwise, continue to break the data into smaller peices. 
 
      // Find the midpoint. 
      int middle = (start + end) / 2; 
 
      // Invoke new tasks, using the subdivided data. 
      Sum subTaskA = new Sum(data, start, middle); 
      Sum subTaskB = new Sum(data, middle, end); 
 
      // Start each subtask by forking. 
      subTaskA.fork(); 
      subTaskB.fork(); 
 
      // Wait for the subtasks to return, and aggregate the results. 
      sum = subTaskA.join() + subTaskB.join(); 
    } 
      // Return the final sum. 
      return sum; 
  } 
} 
 
// Demonstrate parallel execution.  
class RecurTaskDemo {  
  public static void main(String args[]) {  
    // Create a task pool. 
    ForkJoinPool fjp = new ForkJoinPool(); 
 
    double[] nums = new double[5000]; 
 
    // Initialize nums with values that alternate between 
    // positive and negative. 
    for(int i=0; i < nums.length; i++) 
      nums[i] = (double) (((i%2) == 0) ? i : -i) ; 
 
    Sum task = new Sum(nums, 0, nums.length); 
 
    // Start the ForkJoinTasks.  Notice that in this case, 
    // invoke() returns a result. 
    double summation = fjp.invoke(task); 
 
    System.out.println("Summation " + summation); 
  }  
}

