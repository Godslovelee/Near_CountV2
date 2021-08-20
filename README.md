# Near_CountV2A
<<<<<<< HEAD
counter contract

```js
#Initialisation

asconfig.json
{
    "extends":"near-sdk-as/asconfig.json"   
}

#Packages

{
  "name": "near-cout",
  "version": "1.0.0",
  "description": "Counter App",
  "main": "index.js",
  "scripts": {
    "test": "asp"
  },
  "author": "Godslove Lee",
  "license": "ISC",
  "devDependencies": {

    "near-sdk-as": "^3.2.3"
  }
}
    
#UnitTesting

//example.spec.ts
//Implements Uniting testing of index.ts,
//This is as low lovel we can get
import {
  getCounter,
  resetCounter,
  incrementCounter,
  decrementCounter
} from '../index';

import { context, storage, VMContext } from 'near-sdk-as';

describe("Counter ", () => {
  it("should increment by one", () => {
      incrementCounter(1);
      expect(getCounter()).toBe(1, "counter should be one after a single increment.");
  });

  it("getCounter is the same as reading from storage", () => {
      expect(storage.getPrimitive<i32>("counter", 0)).toBe(getCounter(), "storage.getPrimitive<i32>(\"counter\", 0) = getCounter()");
  });

  it("should decrement by one", () => {
      incrementCounter(1);
      decrementCounter(1);
      expect(getCounter()).toBe(0, "counter should be zero after a single decrement.");
  });

  it("should be resetable", () => {
      incrementCounter(1);
      incrementCounter(1);
      resetCounter(); // reset to zero
      expect(getCounter()).toBe(0, "counter should be zero after it is reset."); 
  });
  
  it("should increment multiple times and decrement back to zero", () => {
      incrementCounter(1);
      expect(getCounter()).toBe(1, "0 + 1 = 1");
      incrementCounter(3);
      expect(getCounter()).toBe(4, "1 + 3 = 4");
      decrementCounter(4);
      expect(getCounter()).toBe(0, "4 - 4 = 0");
  });

  it("should be eve's account", () => {
      expect(context.contractName).toBe("eve");
  });
});



```
=======
Refractoring/instantiating a Counter App on Near Block Chain
>>>>>>> 361763528e5e8ff381ddf932125554430a242a73
