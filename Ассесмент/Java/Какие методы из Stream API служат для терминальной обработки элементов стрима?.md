В Java Stream API терминальные операции выполняют обработку элементов стрима и завершают его обработку, возвращая результат или побочный эффект (например, вывод в консоль). 

Основные терминальные методы Stream API:

1. **`forEach`**: Применяет указанный метод к каждому элементу стрима. Этот метод не возвращает результат и используется для обработки каждого элемента (например, для вывода каждого элемента на экран).

   ```java
   stream.forEach(System.out::println);
   ```

2. **`collect`**: Собирает элементы стрима в коллекцию или другую форму структуры данных. Часто используется с коллекторами из класса `Collectors`.

   ```java
   List<String> list = stream.collect(Collectors.toList());
   ```

3. **`reduce`**: Выполняет редукцию элементов стрима с использованием комбинирующей функции и возвращает `Optional` с результатом.

   ```java
   Optional<Integer> result = stream.reduce((a, b) -> a + b);
   ```

4. **`count`**: Возвращает количество элементов в стриме.

   ```java
   long count = stream.count();
   ```

5. **`min` и `max`**: Возвращают минимальный и максимальный элемент стрима соответственно, в зависимости от предоставленного компаратора.

   ```java
   Optional<T> min = stream.min(Comparator.comparing(T::getValue));
   Optional<T> max = stream.max(Comparator.comparing(T::getValue));
   ```

6. **`anyMatch`, `allMatch`, `noneMatch`**: Проверяют элементы стрима на соответствие предикату. `anyMatch` возвращает `true`, если хотя бы один элемент соответствует предикату; `allMatch` возвращает `true`, если все элементы соответствуют предикату; `noneMatch` возвращает `true`, если ни один элемент не соответствует предикату.

   ```java
   boolean anyMatch = stream.anyMatch(predicate);
   boolean allMatch = stream.allMatch(predicate);
   boolean noneMatch = stream.noneMatch(predicate);
   ```

7. **`findFirst` и `findAny`**: Возвращают `Optional` с первым элементом стрима или любым элементом стрима соответственно. Обычно используются для получения элемента из стрима, который соответствует заданным критериям.

   ```java
   Optional<T> first = stream.findFirst();
   Optional<T> any = stream.findAny();
   ```
