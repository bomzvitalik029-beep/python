class Node:
    def __init__(self, data):
        self.data = data   # значение узла
        self.next = None   # ссылка на следующий узел (по умолчанию пусто)


class LinkedList:
    def __init__(self):
        self.head = None   # список пустой — головы нет

    # вставить в голову
    def insert(self, data):
        new_node = Node(data)        # создаём новый узел
        new_node.next = self.head    # новый узел смотрит на бывшую голову
        self.head = new_node         # теперь новый узел — это голова

    # вставить в хвост
    def append(self, data):
        new_node = Node(data)        # создаём новый узел
        if self.head is None:        # если список пустой — новый узел сразу голова
            self.head = new_node
            return
        current = self.head          # начинаем с головы
        while current.next:          # идём вперёд, пока есть следующий
            current = current.next
        current.next = new_node      # последний узел теперь указывает на новый

    # удалить из головы
    def remove(self):
        if self.head is None:        # нечего удалять
            print("Список пуст")
            return None
        removed = self.head.data     # запоминаем значение головы
        self.head = self.head.next   # сдвигаем голову на следующий узел
        return removed               # возвращаем удалённое значение

    # удалить из хвоста
    def delete(self):
        if self.head is None:        # нечего удалять
            print("Список пуст")
            return None
        if self.head.next is None:   # один элемент — просто обнуляем голову
            removed = self.head.data
            self.head = None
            return removed
        current = self.head          # начинаем с головы
        while current.next.next:     # останавливаемся на предпоследнем узле
            current = current.next
        removed = current.next.data  # запоминаем значение хвоста
        current.next = None          # отрезаем хвост
        return removed

    # длина списка
    def size(self):
        count = 0
        current = self.head          # начинаем с головы
        while current:               # идём до конца
            count += 1
            current = current.next
        return count

    def __str__(self):
        result = []
        current = self.head
        while current:               # собираем все значения в список
            result.append(str(current.data))
            current = current.next
        return " -> ".join(result) if result else "[]"   # красивый вывод
            
ll = LinkedList()
 
# insert: вставка в голову
ll.insert(3)
ll.insert(2)
ll.insert(1)
print(ll)           # 1 -> 2 -> 3
 
# append: вставка в хвост
ll.append(4)
ll.append(5)
print(ll)           # 1 -> 2 -> 3 -> 4 -> 5
 
# size
print(ll.size())    # 5
 
# remove: удаление из головы
print("Удалён:", ll.remove())   # 1
print(ll)           # 2 -> 3 -> 4 -> 5
 
# delete: удаление из хвоста
print("Удалён:", ll.delete())   # 5
print(ll)           # 2 -> 3 -> 4
 
print("Размер:",ll.size())    # 3
