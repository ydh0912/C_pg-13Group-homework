#include <stdio.h>

void Sorting(int* pArr, int size);
int max(int* pArr, int size);
int min(int* pArr, int size);

int main() {
	int b[] = { 20, 34, 12, 24, 54, 91, 9, 40, 81, 10 };
	int size = sizeof(b) / sizeof(int);

	int max_pArr = max(b, size);
	int min_pArr = min(b, size);
	printf("최대값 : %d , 최소값 : %d\n", max_pArr, min_pArr);
	printf("\n[정렬 전 배열]\n");
	for (int i = 0; i < size; i++) printf("%d ", b[i]);
	printf("\n[정렬 후 배열]\n");
	Sorting(b, size);

	return 0;
}
//최댓값 최솟값 구하는 함수
int max(int* pArr, int size) {
	int max = -1000;

	for (int i = 0; i < size; i++) {
		if (pArr[i] >= max) {
			max = pArr[i];
		}
	}

	return max;
}
int min(int* pArr, int size) {
	int min = 1000;

	for (int i = 0; i < size; i++) {
		if (pArr[i] <= min) {
			min = pArr[i];
		}
	}

	return min;
}
// 내림차순으로 정렬하는 함수
void Sorting(int* pArr, int size) {
	int temp;
	
	for (int i = 0; i < size - 1; i++) {
		for (int j = i + 1; j < size; j++) {
			if (pArr[i] < pArr[j]) {
				temp = pArr[i];
				pArr[i] = pArr[j];
				pArr[j] = temp;
			}
		}
	}

	for (int i = 0; i < size; i++) {
		printf("%d ", pArr[i]);
	}
	printf("\n");
}
