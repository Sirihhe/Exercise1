### C:

  void* incrementingThreadFunction(){
    for (int j = 0; j < 999999; j++) {
        i++;
      }
      return NULL;
    }

    void* decrementingThreadFunction(){
      for (int j = 0; j < 999999; j++) {
        i--;
      }
      return NULL;
  }

Using void* as return type.

  int main(){
      pthread_t incrementingThread;
      pthread_t decrementingThread;

      pthread_create(&incrementingThread, NULL, incrementingThreadFunction, NULL);
      pthread_create(&decrementingThread, NULL, decrementingThreadFunction, NULL);

      pthread_join(incrementingThread, NULL);
      pthread_join(decrementingThread, NULL);

      printf("The magic number is: %d\n", i);
      return 0;
    }

pthread_join blocking the thread.
The augment terminates -> decrementing
incrementing must finish.
incrementingThread; pthread_t decrementingThread;

### Go:

  func incrementing() {
    for j := 0; j < 1000000; j++ {
      i++
    }
  }

  func decrementing() {
    for j := 0; j < 1000000; j++ {
      i--
    }
  }

  func main() {
      runtime.GOMAXPROCS(runtime.NumCPU())   
	     time.Sleep(10 * time.Millisecond)
	      go decrementing()
        time.Sleep(100*time.Millisecond)
        Println("The magic number is:", i)
}

runtime.GOMAXPROCS(runtime.NumCPU())  ->  hindrer at flere CPU kjører samtidig


### Python:
  def incrementingFunction():
      global i
      for j in range(1000000):
          i = i + 1

        def decrementingFunction():
      global i
      for j in range(1000000):
          i = i - 1



        def main():

      incrementing = Thread(target = incrementingFunction, args = (),)
      decrementing = Thread(target = decrementingFunction, args = (),)

      incrementing.start()
      incrementing.join()

      decrementing.start()
      decrementing.join()

      print("The magic number is %d" % (i))


    main()
