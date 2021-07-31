# Algorithm
###### tags: `HackerRank`

## Simple Array Sum
- 題目
![](https://i.imgur.com/fowMjPs.png)
```c=
/*
 * Complete the 'simpleArraySum' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts INTEGER_ARRAY ar as parameter.
 */

int simpleArraySum(int ar_count, int* ar) {
    int sum = 0;
    int i;
    
    for (i=0; i < ar_count; i++){
        sum += ar[i];
    }
    return sum;
}
```


## Compare the Triplets
- 題目
![](https://i.imgur.com/G8Gn1K2.png)


```c=
int* compareTriplets(int a_count, int* a, int b_count, int* b, int* result_count) {    
    *result_count = 2;
    int *ret = (int *)calloc(2, sizeof(int));
    // calloc(array_size, element_size)
    // calloc will set all element to 0
    
    for (int i = 0; i < a_count; i++) {
        if (a[i] > b[i]) {
            ret[0] += 1;
        } else if (a[i] < b[i]) {
            ret[1] += 1;
        } else {
            continue;
        }
    }
    
    return ret;
}
```

## A Very Big Sum
- 題目
![](https://i.imgur.com/HMhVKxd.png)

```c=
/*
 * Complete the 'aVeryBigSum' function below.
 *
 * The function is expected to return a LONG_INTEGER.
 * The function accepts LONG_INTEGER_ARRAY ar as parameter.
 */

long aVeryBigSum(int ar_count, long* ar) {
    long sum = 0;
    for (int i = 0; i < ar_count; i++) {
        sum += ar[i];
    }

    return sum;
}
```

## Diagonal Difference
- 題目
![](https://i.imgur.com/1MAXWWx.png)

```c=
/*
 * Complete the 'diagonalDifference' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts 2D_INTEGER_ARRAY arr as parameter.
 */

int diagonalDifference(int arr_rows, int arr_columns, int** arr) {
    int left = 0, right = 0;
    
    for (int i = 0; i < arr_rows; i++) {
        for (int j = 0; j < arr_columns; j++) {
            if ((i == j) && (i + j == arr_rows - 1)) {
                left += arr[i][j];
                right += arr[i][j];
            } else if (i == j) {
                left += arr[i][j];
            } else if (i + j == arr_rows - 1) {
                right += arr[i][j];
            } else {
                continue;
            }
        }
    }
    
    return abs(left - right);
}

```

## Plus Minus
- 題目
![](https://i.imgur.com/zyjIf5i.png)

```c=
/*
 * Complete the 'plusMinus' function below.
 *
 * The function accepts INTEGER_ARRAY arr as parameter.
 */

void plusMinus(int arr_count, int* arr) {
    int zero = 0, pos = 0, neg = 0;
    for (int i = 0; i < arr_count; i++) {
        if (arr[i] == 0) {
                zero += 1;
        } else if (arr[i] > 0) {
            pos += 1;
        } else {
            neg += 1;
        }
    }
    
    printf("%.6f\n", pos/(double)arr_count);
    printf("%.6f\n", neg/(double)arr_count);
    printf("%.6f\n", zero/(double)arr_count);
}
```

## Staircase
- 題目
![](https://i.imgur.com/aePrF3o.png)

```c=
/*
 * Complete the 'staircase' function below.
 *
 * The function accepts INTEGER n as parameter.
 */

void staircase(int n) {
    for (int i = 1; i <= n; i++) {
        for (int s = 1; s <= n - i; s++){
            printf(" ");
        }
        
        for (int c = i; c > 0; c--) {
            printf("#");
        }
        printf("\n");
    }
}
```


## Min-Max Sum
- 題目
![](https://i.imgur.com/GgxgglL.png)

```c=
void miniMaxSum(int arr_count, int* arr) {    
    long long int min = arr[0], max = arr[0], sum = 0;
    
    for (int i = 0; i < arr_count; i++) {
        sum += arr[i];
        
        if (arr[i] < min) {
            min = arr[i];
        }
        
        if (arr[i] > max) {
            max = arr[i];
        }
    }
    printf("%lld %lld\n", sum - max, sum - min);

}

```


## Birthday Cake Candles
- 題目
![](https://i.imgur.com/aMGVoHF.png)

```c=
/*
 * Complete the 'birthdayCakeCandles' function below.
 *
 * The function is expected to return an INTEGER.
 * The function accepts INTEGER_ARRAY candles as parameter.
 */

int birthdayCakeCandles(int candles_count, int* candles) {
    int max = candles[0], cnt = 0;
    
    for (int i = 0; i < candles_count; i++) {
        if (candles[i] == max) {
            cnt += 1;
        } else if (candles[i] > max) {
            cnt = 1;
            max = candles[i];
        }
    }
    return cnt;
}
```


## Time Conversion
- 題目 
![](https://i.imgur.com/6UN8f2o.png)

```c=
char* timeConversion(char* s) {
    int hour;
    char *rest = malloc(10 * sizeof(char));
    char *ret = malloc(11 * sizeof(char));
    sscanf(s, "%d:%s", &hour, rest);
    //sscanf 可將特定字串轉換成特定format變數
    
    if (!strncmp(rest + 5, "A", 1)) {
        memset(rest + 5, '\0', 1);
        snprintf(ret, 9, "%02d:%s", hour % 12, rest);
    } else {
        memset(s + 5, '\0', 1);
        snprintf(ret, 9, "%02d:%s", ((hour % 12) + 12) % 24, rest);
    }
    return ret;
}
```

