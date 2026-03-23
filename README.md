1) В массиве представлены данные об n средних чеках покупателей в магазине.
Найти все аномальные выбросы в этом массиве, используя формулу Z-оценки.
Формула для расчета Z-оценки:
Zi = (Xi – μ) / σ, где Xi – значение массива, μ – среднее арифметическое
элементов массива, 𝜎 = √∑(𝑋𝑖−𝜇)2
𝑛−1 – стандартное отклонение
2) Даны 2 текста. Вывести их общие слова.
(для второй задачи не работает русский язык. в выводепишет странные символы. Я пробовал windows.h ConsoleOut(значение) и пробовал сохранять файлы по разному. не помогло
~~~
#include <iostream>
#include <cmath>
#include <cstring>
#include <windows.h>
using namespace std;

int main() {
    setlocale(LC_ALL, "Russian");

    int n, i = 0;
    cin >> n;
    double X[100], m, d = 0, s = 0;
    if (n < 2) {
        cout << "n должно быть >= 2";
        return 0;
    }
    for (i = 0; i < n; i++) {
        cin >> X[i];
        s += X[i];
    }
    cin.ignore(1, '\n');
    m = s / n;
    for (i = 0; i < n; i++) {
        d += ((X[i] - m) * (X[i] - m)) / (n - 1);
    }
    d = sqrt(d);
    cout << m << endl;
    cout << d << endl;


    char s1[200], s2[200];
    cin.getline(s1, 200);
    cin.getline(s2, 200);

    char w1[50], w2[50];
    i = 0;

    while (s1[i] != '\0') {
        while (s1[i] == ' ') i++;
        int k = 0;
        while (s1[i] != ' ' && s1[i] != '\0') {
            w1[k++] = s1[i];
            i++;
        }
        w1[k] = '\0';
        if (k == 0) break;
        int j = 0;
        while (s2[j] != '\0') {
            while (s2[j] == ' ') j++;
            int t = 0;
            while (s2[j] != ' ' && s2[j] != '\0') {
                w2[t++] = s2[j];
                j++;
            }
            w2[t] = '\0';

            if (strcmp(w1, w2) == 0) {
                cout << w1 << " ";
                break;
            }
        }
    }

}
