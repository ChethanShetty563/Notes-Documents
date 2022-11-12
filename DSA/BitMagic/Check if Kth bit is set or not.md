## Example

Input : n = 5 , k=1    Binary rep  n = 00....0101
Outpt: YES

Input : n = 8, k = 2  Binary rep n = 00 .....1000
Output : NO

Input: n = 0 , k = 3  Binary rep n = 00......0000
Output : NO

## Idea for the solution :

#### How do you test the last bit?
``` java
	if(n&1 != 0)
		print("YES")
	else
		print("No")
```

Becuase 1 is yje only number which has last bit as 1 and all other bit as 0 . If we do AND opeartion of n with 1 we get whther the last bit of n is 0 or 1

Using this we can find out whether the given n is odd or not

####How do you check the kth bit?

We mainly need to do bitwise AND with the number only Kth bit set

00.......010....00     Kth bit

The expresssion will be 2^k-1


x = 4 The binary rep  00.....0100 => 4 .  Th posistion can be found using 2^3-1 ==> 4

#### Naive Solution

``` Java
void isSet(int n, int k) {
int x = 1;
for(int i=0'i<k-1;i++) {
	x = x * 2;
}
	if(n & x != 0) {
		print("YES")
		
	}
	else {
	print("No")
	}
}

%%Time Complexity is O(n)%%

	
```

The above for loop calculates the 2 ^k-1 and check with n

Efficient Solution

```Java
void isKthSet(int n, int k) {

int x = (1 << (k-1));
if(n &x != 0){
print("yes")

}
else{
print("No")
}
}
```

