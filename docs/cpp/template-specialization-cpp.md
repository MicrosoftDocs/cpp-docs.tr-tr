---
title: Şablon Uzmanlığı (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- partial specialization of class templates
ms.assetid: f3c67c0b-3875-434a-b8d8-bb47e99cf4f0
ms.openlocfilehash: 7f71c2c3862bd015ba3edcd17aeac85472eb2562
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008915"
---
# <a name="template-specialization-c"></a>Şablon Uzmanlığı (C++)

Sınıf şablonları kısmen uzmanlaşmış olabilir ve elde edilen sınıf hala bir şablondur. Kısmi özelleşme, şablon kodunun bazı durumlarda belirli türler için kısmen özelleştirilme olanağı sağlar; örneğin:

- Şablonda birden çok tür vardır ve bunların yalnızca bazılarının özelleştirilmeleri gerekir. Sonuç, kalan türlerde parametreli bir şablondur.

- Şablon yalnızca bir türe sahiptir, ancak işaretçi, başvuru, üye işaretçisi veya işlev işaretçisi türleri için bir özelleştirme gerekir. Özelleşmenin kendisi, işaret edilen veya başvurulan tür üzerinde hala bir şablondur.

## <a name="example-partial-specialization-of-class-templates"></a>Örnek: sınıf şablonlarının kısmi özelleştirmesi

```cpp
// partial_specialization_of_class_templates.cpp
template <class T> struct PTS {
   enum {
      IsPointer = 0,
      IsPointerToDataMember = 0
   };
};

template <class T> struct PTS<T*> {
   enum {
      IsPointer = 1,
      IsPointerToDataMember = 0
   };
};

template <class T, class U> struct PTS<T U::*> {
   enum {
      IsPointer = 0,
      IsPointerToDataMember = 1
   };
};

struct S{};

extern "C" int printf_s(const char*,...);

int main() {
   printf_s("PTS<S>::IsPointer == %d PTS<S>::IsPointerToDataMember == %d\n",
           PTS<S>::IsPointer, PTS<S>:: IsPointerToDataMember);
   printf_s("PTS<S*>::IsPointer == %d PTS<S*>::IsPointerToDataMember ==%d\n"
           , PTS<S*>::IsPointer, PTS<S*>:: IsPointerToDataMember);
   printf_s("PTS<int S::*>::IsPointer == %d PTS"
           "<int S::*>::IsPointerToDataMember == %d\n",
           PTS<int S::*>::IsPointer, PTS<int S::*>::
           IsPointerToDataMember);
}
```

```Output
PTS<S>::IsPointer == 0 PTS<S>::IsPointerToDataMember == 0
PTS<S*>::IsPointer == 1 PTS<S*>::IsPointerToDataMember ==0
PTS<int S::*>::IsPointer == 0 PTS<int S::*>::IsPointerToDataMember == 1
```

## <a name="example-partial-specialization-for-pointer-types"></a>Örnek: işaretçi türleri için kısmi özelleşme

Herhangi bir türü alan bir şablon koleksiyonu sınıfınız varsa `T` , herhangi bir işaretçi türü alan kısmi bir özelleştirme oluşturabilirsiniz `T*` . Aşağıdaki kod, bir koleksiyon sınıfı şablonunu `Bag` ve koleksiyonun, diziyi bir diziye kopyalamadan önce işaretçi türlerini referans aldığı işaretçi türleri için kısmi bir özelleşme gösterir. Daha sonra koleksiyon, işaret edilen değerleri depolar. Özgün şablon ile, yalnızca işaretçilerin kendisi, verilerin silinme veya değişiklik yapılmasına karşı savunmasız bırakılması halinde depolanır. Koleksiyonun bu özel işaretçi sürümünde, yöntemde null bir işaretçi denetlenecek kod `add` eklenir.

```cpp
// partial_specialization_of_class_templates2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

// Original template collection class.
template <class T> class Bag {
   T* elem;
   int size;
   int max_size;

public:
   Bag() : elem(0), size(0), max_size(1) {}
   void add(T t) {
      T* tmp;
      if (size + 1 >= max_size) {
         max_size *= 2;
         tmp = new T [max_size];
         for (int i = 0; i < size; i++)
            tmp[i] = elem[i];
         tmp[size++] = t;
         delete[] elem;
         elem = tmp;
      }
      else
         elem[size++] = t;
   }

   void print() {
      for (int i = 0; i < size; i++)
         cout << elem[i] << " ";
      cout << endl;
   }
};

// Template partial specialization for pointer types.
// The collection has been modified to check for NULL
// and store types pointed to.
template <class T> class Bag<T*> {
   T* elem;
   int size;
   int max_size;

public:
   Bag() : elem(0), size(0), max_size(1) {}
   void add(T* t) {
      T* tmp;
      if (t == NULL) {   // Check for NULL
         cout << "Null pointer!" << endl;
         return;
      }

      if (size + 1 >= max_size) {
         max_size *= 2;
         tmp = new T [max_size];
         for (int i = 0; i < size; i++)
            tmp[i] = elem[i];
         tmp[size++] = *t;  // Dereference
         delete[] elem;
         elem = tmp;
      }
      else
         elem[size++] = *t; // Dereference
   }

   void print() {
      for (int i = 0; i < size; i++)
         cout << elem[i] << " ";
      cout << endl;
   }
};

int main() {
   Bag<int> xi;
   Bag<char> xc;
   Bag<int*> xp; // Uses partial specialization for pointer types.

   xi.add(10);
   xi.add(9);
   xi.add(8);
   xi.print();

   xc.add('a');
   xc.add('b');
   xc.add('c');
   xc.print();

   int i = 3, j = 87, *p = new int[2];
   *p = 8;
   *(p + 1) = 100;
   xp.add(&i);
   xp.add(&j);
   xp.add(p);
   xp.add(p + 1);
   p = NULL;
   xp.add(p);
   xp.print();
}
```

```Output
10 9 8
a b c
Null pointer!
3 87 8 100
```

## <a name="example-define-partial-specialization-so-one-type-is-int"></a>Örnek: bir tür için kısmi özelleşme tanımlayın `int`

Aşağıdaki örnek, herhangi iki türden çiftleri alan bir şablon sınıfını tanımlar ve sonra türlerden birinin olması için bu şablon sınıfının özelleşmiş bir özelleştirmesi tanımlar **`int`** . Özelleşme, tamsayı temelinde basit bir kabarcık sıralaması uygulayan ek bir sıralama yöntemi tanımlar.

```cpp
// partial_specialization_of_class_templates3.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

template <class Key, class Value> class Dictionary {
   Key* keys;
   Value* values;
   int size;
   int max_size;
public:
   Dictionary(int initial_size) :  size(0) {
      max_size = 1;
      while (initial_size >= max_size)
         max_size *= 2;
      keys = new Key[max_size];
      values = new Value[max_size];
   }
   void add(Key key, Value value) {
      Key* tmpKey;
      Value* tmpVal;
      if (size + 1 >= max_size) {
         max_size *= 2;
         tmpKey = new Key [max_size];
         tmpVal = new Value [max_size];
         for (int i = 0; i < size; i++) {
            tmpKey[i] = keys[i];
            tmpVal[i] = values[i];
         }
         tmpKey[size] = key;
         tmpVal[size] = value;
         delete[] keys;
         delete[] values;
         keys = tmpKey;
         values = tmpVal;
      }
      else {
         keys[size] = key;
         values[size] = value;
      }
      size++;
   }

   void print() {
      for (int i = 0; i < size; i++)
         cout << "{" << keys[i] << ", " << values[i] << "}" << endl;
   }
};

// Template partial specialization: Key is specified to be int.
template <class Value> class Dictionary<int, Value> {
   int* keys;
   Value* values;
   int size;
   int max_size;
public:
   Dictionary(int initial_size) :  size(0) {
      max_size = 1;
      while (initial_size >= max_size)
         max_size *= 2;
      keys = new int[max_size];
      values = new Value[max_size];
   }
   void add(int key, Value value) {
      int* tmpKey;
      Value* tmpVal;
      if (size + 1 >= max_size) {
         max_size *= 2;
         tmpKey = new int [max_size];
         tmpVal = new Value [max_size];
         for (int i = 0; i < size; i++) {
            tmpKey[i] = keys[i];
            tmpVal[i] = values[i];
         }
         tmpKey[size] = key;
         tmpVal[size] = value;
         delete[] keys;
         delete[] values;
         keys = tmpKey;
         values = tmpVal;
      }
      else {
         keys[size] = key;
         values[size] = value;
      }
      size++;
   }

   void sort() {
      // Sort method is defined.
      int smallest = 0;
      for (int i = 0; i < size - 1; i++) {
         for (int j = i; j < size; j++) {
            if (keys[j] < keys[smallest])
               smallest = j;
         }
         swap(keys[i], keys[smallest]);
         swap(values[i], values[smallest]);
      }
   }

   void print() {
      for (int i = 0; i < size; i++)
         cout << "{" << keys[i] << ", " << values[i] << "}" << endl;
   }
};

int main() {
   Dictionary<char*, char*>* dict = new Dictionary<char*, char*>(10);
   dict->print();
   dict->add("apple", "fruit");
   dict->add("banana", "fruit");
   dict->add("dog", "animal");
   dict->print();

   Dictionary<int, char*>* dict_specialized = new Dictionary<int, char*>(10);
   dict_specialized->print();
   dict_specialized->add(100, "apple");
   dict_specialized->add(101, "banana");
   dict_specialized->add(103, "dog");
   dict_specialized->add(89, "cat");
   dict_specialized->print();
   dict_specialized->sort();
   cout << endl << "Sorted list:" << endl;
   dict_specialized->print();
}
```

```Output
{apple, fruit}
{banana, fruit}
{dog, animal}
{100, apple}
{101, banana}
{103, dog}
{89, cat}

Sorted list:
{89, cat}
{100, apple}
{101, banana}
{103, dog}
```
