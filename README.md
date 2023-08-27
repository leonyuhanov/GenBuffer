# GenBuffer
A generic buffer using linked lists to do anything you like. This is a utilty class for appliactions where you have a ton of incoming data that can be safely poped out in the main look whilst its beeing filled up.

# Example use

````
#include "genBuffer.h"

void setup()
{
  genBuffer globalBuffer;
}

void loop()
{
  uint8_t* currentBlock;
  //check if theres anythign in the buffer
  if(globalBuffer.totalNodes)
  {
    currentBlock = new uint8_t[globalBuffer.getDataLen()];
    currentBlock = globalBuffer.getData();
    globalBuffer.deleteFirst();
  }
  yield();
}

void addToBuffer()
{
  const unsigned int dataLength = 100;
  uint8_t* someData[dataLength];
  globalBuffer.add(someData, dataLength);
}
````

