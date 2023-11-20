# Lab Report 3

## Part 1
The bug that I choose to focus is reverseInPlace() in ArrayExamples.

### The failure-inducing input for the buggy program is

```
@Test
  public void testReverseInPlace1() {
    int[] input1 = { 4, 7, 12, 22 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[] {22,12,7,4}, input1);
  }
```

### The input that doesn’t induce a failure:

```

@Test
public void testReverseInPlace2(){
	int[] input1 = {1};
	ArrayExamples.reverseInPlace(input1);
	assertArrayEquals(new int[]{1}, input1);
}
```

### The symptom:
<img width="1038" alt="Screenshot 2023-11-19 at 10 42 52 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/e8b76902-144d-4f67-95fa-49fd3f3a411a">

### The bug before code change:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
### The bug before code change:
```
static void reverseInPlace(int[] arr) {
   for (int i = 0; i < arr.length / 2; i += 1) {
     int temp = arr[i];
     arr[i] = arr[arr.length - i - 1];
     arr[arr.length-i-1] = temp;
   }
```

### Successful output after debug:
<img width="973" alt="Screenshot 2023-11-19 at 10 18 42 PM" src="https://github.com/Christina-xizi/cse15l-lab-reports/assets/146885167/9298355c-2bd4-4788-93a0-9a0e08a91f9d">

### Explanation: 
The bug in the original code was that it attempted to reverse the array in place, but the logic was flawed. It looped through the entire array and assigned each element to the value of its mirrored counterpart from the end of the array. However, this approach resulted in overwriting the original values before they could be correctly swapped, leading to incorrect results.

The fix addresses this issue by iterating only up to half of the array length `arr.length/2` in the loop. Within each iteration, it swaps the elements at the current position `arr[i]` with their mirrored counterparts at the end of the array `arr[arr.length - i - 1]`. This ensures that each element is correctly swapped with its corresponding element from the other end of the array, effectively reversing the array in place. The introduction of the `temp` variable is crucial for temporarily storing the original value of `arr[i]` before the swap.

## Part 2
I choose to focus on the grep command and explore four command-line options or alternate ways to use it.
