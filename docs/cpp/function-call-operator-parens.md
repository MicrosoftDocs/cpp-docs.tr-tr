---
title: 'İşlev Çağırma İşleci: ()'
ms.date: 11/04/2016
helpviewer_keywords:
- ( ) function call operator
- function calls, C++ functions
- () function call operator
- postfix operators [C++]
- function calls, operator
- functions [C++], function-call operator
- function call operator ()
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
ms.openlocfilehash: 08c60ff261e944ed5b54b51a013a6d331f212154
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179776"
---
# <a name="function-call-operator-"></a>İşlev Çağırma İşleci: ()

Bir sonek ifadesi ve ardından işlev çağrısı işleci **()** , bir işlev çağrısını belirtir.

## <a name="syntax"></a>Sözdizimi

```
postfix-expression
( [argument-expression-list ] )
```

## <a name="remarks"></a>Açıklamalar

İşlev çağrısı işlecinin bağımsız değişkenleri, virgülle ayrılmış olarak sıfır veya daha fazla ifade (işlevin gerçek bağımsız değişkenleri).

*Sonek ifadesi* bir işlev adresi (örneğin, bir işlev tanımlayıcısı veya bir işlev işaretçisinin değeri) olarak değerlendirilmelidir ve *bağımsız değişken-ifade listesi* , değerleri (bağımsız değişkenler) işlevine geçilen ifadelerin (virgülle ayrılmış) bir listesidir. *Bağımsız değişken-ifade listesi* bağımsız değişkeni boş olabilir.

*Sonek ifadesi* şu türlerden biri olmalıdır:

- İşlev türü döndüren işlev `T`. Örnek bir bildirim

    ```cpp
    T func( int i )
    ```

- `T`türü döndüren işlevin işaretçisi. Örnek bir bildirim

    ```cpp
    T (*func)( int i )
    ```

- `T`türü döndüren bir işleve başvuru. Örnek bir bildirim

    ```cpp
    T (&func)(int i)
    ```

- Üye işaretçisi işlev başvurusu `T`türü döndürüyor. Örnek işlev çağrıları

    ```cpp
    (pObject->*pmf)();
    (Object.*pmf)();
    ```

## <a name="example"></a>Örnek

Aşağıdaki örnek, üç bağımsız değişkenle `strcat_s` Standart Kitaplık işlevini çağırır:

```cpp
// expre_Function_Call_Operator.cpp
// compile with: /EHsc

#include <iostream>
#include <string>

// C++ Standard Library name space
using namespace std;

int main()
{
    enum
    {
        sizeOfBuffer = 20
    };

    char s1[ sizeOfBuffer ] = "Welcome to ";
    char s2[ ] = "C++";

    strcat_s( s1, sizeOfBuffer, s2 );

    cout << s1 << endl;
}
```

```Output
Welcome to C++
```

## <a name="function-call-results"></a>İşlev çağrısı sonuçları

İşlev bir başvuru türü olarak bildirilemediği sürece, bir işlev çağrısı r-değeri olarak değerlendirilir. Başvuru dönüş türü olan işlevler, l değerleri olarak değerlendirilir ve atama ifadesinin sol tarafında aşağıdaki gibi kullanılabilir:

```cpp
// expre_Function_Call_Results.cpp
// compile with: /EHsc
#include <iostream>
class Point
{
public:
    // Define "accessor" functions as
    // reference types.
    unsigned& x() { return _x; }
    unsigned& y() { return _y; }
private:
    unsigned _x;
    unsigned _y;
};

using namespace std;
int main()
{
    Point ThePoint;

    ThePoint.x() = 7;           // Use x() as an l-value.
    unsigned y = ThePoint.y();  // Use y() as an r-value.

    // Use x() and y() as r-values.
    cout << "x = " << ThePoint.x() << "\n"
         << "y = " << ThePoint.y() << "\n";
}
```

Önceki kod, *x* ve *y* koordinatlarını temsil eden özel veri nesneleri içeren `Point`adlı bir sınıfı tanımlar. Bu veri nesnelerinin değiştirilmesi ve değerlerinin alınması gerekir. Bu program, böyle bir sınıf için yalnızca birkaç tasarımdan biridir; `GetX` ve `SetX` veya `GetY` kullanımı ve `SetY` işlevleri başka bir olası tasarımdır.

Sınıf türleri, sınıf türlerine işaretçiler veya sınıf türlerine yapılan başvurular döndüren işlevler, üye seçim işleçleri için sol işlenen olarak kullanılabilir. Bu nedenle, aşağıdaki kod geçerlidir:

```cpp
// expre_Function_Results2.cpp
class A {
public:
   A() {}
   A(int i) {}
   int SetA( int i ) {
      return (I = i);
   }

   int GetA() {
      return I;
   }

private:
   int I;
};

A func1() {
   A a = 0;
   return a;
}

A* func2() {
   A *a = new A();
   return a;
}

A& func3() {
   A *a = new A();
   A &b = *a;
   return b;
}

int main() {
   int iResult = func1().GetA();
   func2()->SetA( 3 );
   func3().SetA( 7 );
}
```

İşlevler yinelemeli olarak çağrılabilir. İşlev bildirimleri hakkında daha fazla bilgi için bkz. [işlevler](functions-cpp.md). İlgili malzemeler [çeviri birimleri ve bağlantı](../cpp/program-and-linkage-cpp.md)' nda bulunur.

## <a name="see-also"></a>Ayrıca bkz.

[Son Ek İfadeleri](../cpp/postfix-expressions.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[İşlev Çağrısı](../c-language/function-call-c.md)
