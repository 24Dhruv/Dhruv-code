# Dhruv-code
This is my first repo
<br>
written by dhruv (Khandelwal)

public static void mergeSort(int[] arr) {
    if (arr == null || arr.length <= 1)
        return;
    int n = arr.length;
    int[] temp = new int[n];
    mergeSort(arr, temp, 0, n - 1);
}

private static void mergeSort(int[] arr, int[] temp, int left, int right) {
    if (left < right) {
        int mid = left + (right - left) / 2;
        // Sort first and second halves
        mergeSort(arr, temp, left, mid);
        mergeSort(arr, temp, mid + 1, right);
        // Merge the sorted halves
        merge(arr, temp, left, mid, right);
    }
}

private static void merge(int[] arr, int[] temp, int left, int mid, int right) {
    for (int i = left; i <= right; i++) {
        temp[i] = arr[i];
    }
    int i = left;
    int j = mid + 1;
    int k = left;
    while (i <= mid && j <= right) {
        if (temp[i] <= temp[j]) {
            arr[k] = temp[i];
            i++;
        } else {
            arr[k] = temp[j];
            j++;
        }
        k++;
    }
    while (i <= mid) {
        arr[k] = temp[i];
        k++;
        i++;
    }
}
public static void main(String[] args) {
    int[] arr = {5, 2, 8, 1, 9, 3};
    // Sorting the array using merge sort
    mergeSort(arr);
    // Printing the sorted array
    System.out.println("Sorted array:");
    for (int num : arr) {
        System.out.print(num + " ");
    }
    System.out.println();
}}
