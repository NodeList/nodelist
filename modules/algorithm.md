# 算法

### 1. 输入 3 个数：k，n，m；其中 k 为十进制数，m 代表 m 进制数，求 k 的 m 进制数中含有多少个 n。

-   解析：先求出 k 的 m 进制数，再判断里面含有多少个 n。（`parseInt('num', rix); // 将rix进制的num转换为10进制数`）
    ```javascript
    function returnCount(k, n, m) {
        var count = 0;
        var km = k.toString(4);
        for (var i = 0; i < km.length; i++) {
            if (km[i] == n) {
                count += 1;
            }
        }
        return count;
    }
    ```

### 2. 有一个整型数组，从数组中取出两个最大的值，用大值减去小值，若结果不为 0，则将结果放回数组，重复上面操作，直到数组中只有一个元素或为空，若只有一个元素，则返回该元素，若为空，则返回 0

-   解析：我用最笨的方法，先取出两个最大值并在数组中删除，判断大值减去小值的结果，若不为 0 则放回数组，再取出两个最大的值重复操作。每次取最大值之前先判断数组的长度 length，若为 1，则返回该元素，若为 0，则返回 0，否则递归执行该操作。
    ```javascript
    function max(arr) {
        if (arr.length === 0) {
            return 0;
        } else if (arr.length === 1) {
            return arr[0];
        } else {
            let max1 = Math.max(...arr);
            arr.splice(find(arr, max1), 1);
            let max2 = Math.max(...arr);
            arr.splice(find(arr, max2), 1);
            if (max1 - max2 != 0) {
                arr.push(max1 - max2);
            }
            console.log(arr);
            // 需要对递归方法进行递归
            return max(arr);
        }
    }
    function find(arr, num) {
        return arr.findIndex((item) => {
            return item == num;
        });
    }
    console.log(max([1, 7, 9, 15, 44]));
    ```

### 3.
