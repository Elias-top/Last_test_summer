- Автор : Пилипчук Илья Викторович
- Ссылка на профиль GB: https://gb.ru/users/3ebc6b68-0b29-40a6-8145-01f619b213be
- Ссылка на профиль GitHub: https://github.com/Elias-top

# **Условие задачи:**

*Написать программу, которая из имеющегося массива строк формирует новый массив из строк, длина которых меньше, либо равна 3 символам. Первоначальный массив можно ввести с клавиатуры, либо задать на старте выполнения алгоритма. При решении не рекомендуется пользоваться коллекциями, лучше обойтись исключительно массивами.*

## **Диаграмма решения задачи:**

![Диаграмма решения задачи](/Program_State.jpg)

## **Программный код**
```
string []my_array = {"1234", "1567", "-2", "computer science", "mam", "i", "2444j", "Russian", "DEN"};

string []result_array = GetStrArrayLessUserNum(3, my_array);

PrintArrayToConsole(result_array);

static string [] GetStrArrayLessUserNum(int user_num, string[] user_array)
{
    int temp_index = 0;

    string []temp_result_array = new string [user_array.Length];

    for(int i = 0; i < user_array.Length; i++)
    {
        if(user_array[i].Length <= user_num)
        {
            temp_result_array[temp_index] = user_array[i];
            temp_index ++;
        }
    }
    string []result_array = new string [temp_index];

    for(int i = 0; i < temp_index; i++)
    {
        result_array[i] = temp_result_array[i];
    }
    return result_array;
}

static void PrintArrayToConsole(string[] array)
{
    Console.WriteLine();
    Console.Write("[");
    for(int i = 0; i < array.Length; i++)
    {
        if(array.Length == i + 1)
        {
            Console.Write(array[array.Length - 1]);
            break;
        }

        Console.Write($"\"{array[i]}\", ");
    }
    Console.Write("]");
    Console.WriteLine();
}
```
### Результат вывода программы: ["-2", "mam", "i", DEN]

