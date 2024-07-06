## 25A - IQ test
### Problem Statement
Bob is preparing to pass IQ test. The most frequent task in this test is to find out which one of the given n numbers differs from the others. Bob observed that one number usually differs from the others in evenness. Help Bob — to check his answers, he needs a program that among the given n numbers finds one that is different in evenness.
### Python Solution
```python
n = int(input())
numbers = list(map(int, input().split()))


def find_index(numbers, n):
    even = 0
    odd = 0
    for i in range(n):
        if numbers[i] % 2 == 0:
            even += 1
        else:
            odd += 1
        if even == 1 and odd > 1:
            for n in numbers:
                if n % 2 == 0:
                    return numbers.index(n) + 1
        if odd == 1 and even > 1:
            for n in numbers:
                if n % 2 != 0:
                    return numbers.index(n) + 1
print(find_index(numbers, n))
```
