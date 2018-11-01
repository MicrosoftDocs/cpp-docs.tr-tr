---
title: Sınıf Şablonları
ms.date: 11/04/2016
helpviewer_keywords:
- classes [C++], operating on type
- class templates
- templates, class templates
ms.assetid: 633a53c8-24ee-4c23-8c88-e7c3cb0b7ac3
ms.openlocfilehash: 1bf384967af9d6d639e11df882751bbdaf1b0aa6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660323"
---
# <a name="class-templates"></a>Sınıf Şablonları

Bu konuda, C++ sınıf şablonları için özel kurallar açıklanmaktadır.

## <a name="member-functions-of-class-templates"></a>Sınıf şablonlarının üye işlevleri

Üye işlevleri, bir sınıf şablonunun içinde veya dışında tanımlanabilir. Sınıf şablonunun dışında tanımlanmışlarsa, işlev şablonu gibi tanımlanırlar.

```cpp
// member_function_templates1.cpp
template<class T, int i> class MyStack
{
    T*  pStack;
    T StackBuffer[i];
    static const int cItems = i * sizeof(T);
public:
    MyStack( void );
    void push( const T item );
    T& pop( void );
};

template< class T, int i > MyStack< T, i >::MyStack( void )
{
};

template< class T, int i > void MyStack< T, i >::push( const T item )
{
};

template< class T, int i > T& MyStack< T, i >::pop( void )
{
};

int main()
{
}
```

Şablon sınıf üyesi işlevinde olduğu gibi, sınıf oluşturucusu üye işlevi tanımının şablon bağımsız değişkeni listesini iki kez içerdiğini unutmayın.

Üye işlevleri, aşağıdaki örnekte olduğu gibi ek parametreler belirterek işlev şablonları olabilir.

```cpp
// member_templates.cpp
template<typename T>
class X
{
public:
   template<typename U>
   void mf(const U &u);
};

template<typename T> template <typename U>
void X<T>::mf(const U &u)
{
}

int main()
{
}
```

## <a name="nested-class-templates"></a>İç içe geçmiş sınıf şablonları

Şablonları sınıflar veya sınıf şablonları içinde tanımlanan, bu durumda bunlar için üye şablonları adlandırılır. Sınıf üye şablonları, iç içe geçmiş sınıf şablonları adlandırılır. İşlevleri, üye şablonları açıklanmıştır [üye işlev şablonları](../cpp/member-function-templates.md).

İç içe geçmiş sınıf şablonları, dış sınıf kapsamı içinde sınıf şablonları olarak bildirilir. Bunlar, içinde veya kapsayan sınıfa dışında tanımlanabilir.

Aşağıdaki kodda, sıradan bir sınıf içinde iç içe geçmiş sınıf şablonu gösterilmektedir.

```cpp
// nested_class_template1.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class X
{

   template <class T>
   struct Y
   {
      T m_t;
      Y(T t): m_t(t) { }
   };

   Y<int> yInt;
   Y<char> yChar;

public:
   X(int i, char c) : yInt(i), yChar(c) { }
   void print()
   {
      cout << yInt.m_t << " " << yChar.m_t << endl;
   }
};

int main()
{
   X x(1, 'a');
   x.print();
}
```

```cpp
// nested_class_template2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

template <class T>
class X
{
   template <class U> class Y
   {
      U* u;
   public:
      Y();
      U& Value();
      void print();
      ~Y();
   };

   Y<int> y;
public:
   X(T t) { y.Value() = t; }
   void print() { y.print(); }
};

template <class T>
template <class U>
X<T>::Y<U>::Y()
{
   cout << "X<T>::Y<U>::Y()" << endl;
   u = new U();
}

template <class T>
template <class U>
U& X<T>::Y<U>::Value()
{
   return *u;
}

template <class T>
template <class U>
void X<T>::Y<U>::print()
{
   cout << this->Value() << endl;
}

template <class T>
template <class U>
X<T>::Y<U>::~Y()
{
   cout << "X<T>::Y<U>::~Y()" << endl;
   delete u;
}

int main()
{
   X<int>* xi = new X<int>(10);
   X<char>* xc = new X<char>('c');
   xi->print();
   xc->print();
   delete xi;
   delete xc;
}

//Output:
X<T>::Y<U>::Y()
X<T>::Y<U>::Y()
10
99
X<T>::Y<U>::~Y()
X<T>::Y<U>::~Y()
```

Yerel sınıfların üye şablonlarına sahip olmasına izin verilmez.

## <a name="template-friends"></a>Şablon arkadaşları

Sınıf şablonları olabilir [arkadaş](friend-cpp.md). Bir sınıf veya sınıf şablonu, işlev ya da işlev şablonu şablon sınıfının arkadaşı olabilir. Arkadaşlar, sınıf şablonunun veya işlev şablonunun da uzmanlıkları olabilir, ancak kısmi uzmanlıklar olamaz.

Aşağıdaki örnekte, bir arkadaş işlevi sınıf şablonu içinde işlev şablonu olarak tanımlanır. Bu kod, şablonun her örneği için arkadaş işlevinin sürümünü oluşturur. Bu yapı, arkadaş işleviniz sınıfla aynı şablon parametrelerine bağlıysa yararlı olur.

```cpp
// template_friend1.cpp
// compile with: /EHsc

#include <iostream>
using namespace std;

template <class T> class Array {
   T* array;
   int size;

public:
   Array(int sz): size(sz) {
      array = new T[size];
      memset(array, 0, size * sizeof(T));
   }

   Array(const Array& a) {
      size = a.size;
      array = new T[size];
      memcpy_s(array, a.array, sizeof(T));
   }

   T& operator[](int i) {
      return *(array + i);
   }

   int Length() { return size; }

   void print() {
      for (int i = 0; i < size; i++)
         cout << *(array + i) << " ";

      cout << endl;
   }

   template<class T>
   friend Array<T>* combine(Array<T>& a1, Array<T>& a2);
};

template<class T>
Array<T>* combine(Array<T>& a1, Array<T>& a2) {
   Array<T>* a = new Array<T>(a1.size + a2.size);
   for (int i = 0; i < a1.size; i++)
      (*a)[i] = *(a1.array + i);

   for (int i = 0; i < a2.size; i++)
      (*a)[i + a1.size] = *(a2.array + i);

   return a;
}

int main() {
   Array<char> alpha1(26);
   for (int i = 0 ; i < alpha1.Length() ; i++)
      alpha1[i] = 'A' + i;

   alpha1.print();

   Array<char> alpha2(26);
   for (int i = 0 ; i < alpha2.Length() ; i++)
      alpha2[i] = 'a' + i;

   alpha2.print();
   Array<char>*alpha3 = combine(alpha1, alpha2);
   alpha3->print();
   delete alpha3;
}
//Output:
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
a b c d e f g h i j k l m n o p q r s t u v w x y z
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z a b c d e f g h i j k l m n o p q r s t u v w x y z
```

Sonraki örnekte, şablon uzmanlığı olan bir arkadaş bulunmaktadır. İşlev şablonu uzmanlığı, orijinal şablon bir arkadaşsa otomatik olarak arkadaş olur.

Aşağıdaki kodda arkadaş bildiriminden önceki yorumun gösterdiği gibi şablonun yalnızca özel sürümü de bildirilebilir. Bunu yaparsanız, arkadaş şablonu uzmanlığının tanımını şablon sınıfının dışına yerleştirmeniz gerekir.

```cpp
// template_friend2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

template <class T>
class Array;

template <class T>
void f(Array<T>& a);

template <class T> class Array
{
    T* array;
    int size;

public:
    Array(int sz): size(sz)
    {
        array = new T[size];
        memset(array, 0, size * sizeof(T));
    }
    Array(const Array& a)
    {
        size = a.size;
        array = new T[size];
        memcpy_s(array, a.array, sizeof(T));
    }
    T& operator[](int i)
    {
        return *(array + i);
    }
    int Length()
    {
        return size;
    }
    void print()
    {
        for (int i = 0; i < size; i++)
        {
            cout << *(array + i) << " ";
        }
        cout << endl;
    }
    // If you replace the friend declaration with the int-specific
    // version, only the int specialization will be a friend.
    // The code in the generic f will fail
    // with C2248: 'Array<T>::size' :
    // cannot access private member declared in class 'Array<T>'.
    //friend void f<int>(Array<int>& a);

    friend void f<>(Array<T>& a);
};

// f function template, friend of Array<T>
template <class T>
void f(Array<T>& a)
{
    cout << a.size << " generic" << endl;
}

// Specialization of f for int arrays
// will be a friend because the template f is a friend.
template<> void f(Array<int>& a)
{
    cout << a.size << " int" << endl;
}

int main()
{
    Array<char> ac(10);
    f(ac);

    Array<int> a(10);
    f(a);
}
//Output:
10 generic
10 int
```

Sonraki örnekte, bir sınıf şablonu içerisinde bildirilen arkadaş sınıf şablonu gösterilmektedir. Sınıf şablonu, daha sonra arkadaş sınıfı için şablon bağımsız değişkeni olarak kullanılır. Arkadaş sınıfı şablonları, bildirildikleri sınıf şablonunun dışında tanımlanmalıdır. Arkadaş şablonunun uzmanlıkları veya kısmi uzmanlıkları da orijinal sınıf şablonunun arkadaşlarıdır.

```cpp
// template_friend3.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

template <class T>
class X
{
private:
   T* data;
   void InitData(int seed) { data = new T(seed); }
public:
   void print() { cout << *data << endl; }
   template <class U> friend class Factory;
};

template <class U>
class Factory
{
public:
   U* GetNewObject(int seed)
   {
      U* pu = new U;
      pu->InitData(seed);
      return pu;
   }
};

int main()
{
   Factory< X<int> > XintFactory;
   X<int>* x1 = XintFactory.GetNewObject(65);
   X<int>* x2 = XintFactory.GetNewObject(97);

   Factory< X<char> > XcharFactory;
   X<char>* x3 = XcharFactory.GetNewObject(65);
   X<char>* x4 = XcharFactory.GetNewObject(97);
   x1->print();
   x2->print();
   x3->print();
   x4->print();
}
//Output:
65
97
A
a
```

## <a name="reuse-of-template-parameters"></a>Şablon parametrelerinin yeniden kullanımı

Şablon parametreleri şablon parametre listesinde yeniden kullanılabilir. Örneğin, aşağıdaki koda izin verilir:

```cpp
// template_specifications2.cpp

class Y
{
};
template<class T, T* pT> class X1
{
};
template<class T1, class T2 = T1> class X2
{
};

Y aY;

X1<Y, &aY> x1;
X2<int> x2;

int main()
{
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Şablonlar](../cpp/templates-cpp.md)