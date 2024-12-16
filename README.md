# binary_search_recursive
I wrote the binary search as a recursive function.


#include <stdio.h>

int binary_search_recursive(int arr[], int low, int high, int search) {
    if (high >= low) {
        int mid = (low + high) / 2;

        if (arr[mid] == search) {
            return mid;
        }
        if (arr[mid] > search) {
			return binary_search_recursive(arr, low, mid - 1, search);
        }
			return binary_search_recursive(arr, mid + 1, high, search);
    }
    return -1;
}

int main() {
    int arr[] = {2, 3, 4, 10, 40};
    int size = sizeof(arr) / sizeof(arr[0]);
    int search;

    printf("Which number do you want to call? ");
    scanf("%d", &search);

    int result = binary_search_recursive(arr, 0, size - 1, search);

    if (result != -1) {
        printf("Number: %d, Found at index %d of the index.\n", search, result);
    } else {
        printf("Number: %d, not found in the series.\n", search);
    }

    return 0;
}
