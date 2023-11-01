Part 1 - Bugs

Junit Tests:
```
@Test
  public void testReversed1(){
    //Test w/ a failure-inducing input for the buggy program
    int[] input1 = { 1, 2, 3};
    assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input1));
  }

  @Test
  public void testReversed2(){
    //Test w/ an input that doesn’t induce a failure
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```

Symptom:
![Image](Screenshot 2023-10-30 at 8.09.15 PM.png)

Before and After Reversed Method Code:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

The fix addresses the issue of the buggy program returning the original array instead of the new one. It also makes it so the new array is the one getting changed within the for loop in order to return a new separate array with all the elements of the input array in reverse order.

Part 2 - Researching Commands
