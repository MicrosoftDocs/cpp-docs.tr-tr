---
description: 'Hakkında daha fazla bilgi edinin: Işlev çağırma Işleci: ()'
title: 'İşlev çağırma işleci: ()'
ms.date: 06/11/2020
helpviewer_keywords:
- ( ) function call operator
- function calls, C++ functions
- () function call operator
- postfix operators [C++]
- function calls, operator
- functions [C++], function-call operator
- function call operator ()
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
no-loc:
- opt
ms.openlocfilehash: 351674f345c7213a3c164ff88e9a165775088c68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344568"
---
# <a name="function-call-operator-"></a>İşlev Çağırma İşleci: ()

İşlev çağrısı, *`postfix-expression`* bir işlev veya çağrılabilir bir nesne ve ardından işlev çağrısı işleci tarafından değerlendirilen bir ifade tarafından oluşturulan bir türüdür **`()`** . Bir nesne `operator ()` , nesne için işlev çağrısı semantiğini sağlayan bir işlev bildirebilir.

## <a name="syntax"></a>Syntax

> *`postfix-expression`*:\
> &emsp;*`postfix-expression`* **`(`** *`argument-expression-list`* <sub>opt</sub> **`)`**

## <a name="remarks"></a>Açıklamalar

İşlev çağrısı işlecinin bağımsız değişkenleri *`argument-expression-list`* , virgülle ayrılmış bir ifade listesinden gelir. Bu ifadelerin değerleri bağımsız değişken olarak işleve geçirilir. *Bağımsız değişken-ifade listesi* boş olabilir. C++ 17 öncesi, işlev ifadesinin ve bağımsız değişken ifadelerinin değerlendirilme sırası belirtilmemiş ve herhangi bir sırada gerçekleşebilir. C++ 17 ve üzeri sürümlerde, işlev ifadesi herhangi bir bağımsız değişken ifadeden veya varsayılan bağımsız değişkenlerden önce değerlendirilir. Bağımsız değişken ifadeleri belirsiz bir sırayla değerlendirilir.

*`postfix-expression`* Çağrısı yapılacak işlev olarak değerlendirilir. Bu, birkaç formdan herhangi birini alabilir:

- bir işlev tanımlayıcısı, geçerli kapsamda veya belirtilen işlev bağımsız değişkenlerinin herhangi birinin kapsamında görünür,
- bir işlev, bir işlev işaretçisi, çağrılabilir nesne veya bir başvurusu için değerlendirilen bir ifade
- açık veya zımni bir üye işlev erişimcisi
- bir üye işlevine başvuru yapılan bir işaretçiye başvurduğunu.

*`postfix-expression`* Aşırı yüklenmiş bir işlev tanımlayıcısı veya aşırı yüklenmiş üye işlev erişimcisi olabilir. Aşırı yükleme çözümlemesi kuralları, çağrılacak gerçek işlevi belirleyebilir. Üye işlevi sanal ise, çağrılacak işlev çalışma zamanında belirlenir.

Bazı örnek bildirimler:

- İşlevin türü döndürüyor `T` . Örnek bir bildirim

    ```cpp
    T func( int i );
    ```

- Tür döndüren bir işlevin işaretçisi `T` . Örnek bir bildirim

    ```cpp
    T (*func)( int i );
    ```

- Tür döndüren bir işleve başvuru `T` . Örnek bir bildirim

    ```cpp
    T (&func)(int i);
    ```

- Üye işaretçisi işlevine başvuru döndüren tür `T` . Örnek işlev çağrıları

    ```cpp
    (pObject->*pmf)();
    (Object.*pmf)();
    ```

## <a name="example"></a>Örnek

Aşağıdaki örnek, standart kitaplık işlevini `strcat_s` üç bağımsız değişkenle çağırır:

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

İşlev bir başvuru türü olarak bildirilemediği sürece bir işlev çağrısı rvalue olarak değerlendirilir. Başvuru dönüş türleri olan işlevler lvalues olarak değerlendirilir. Bu işlevler, burada görüldüğü gibi, atama ifadesinin sol tarafında kullanılabilir:

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

Önceki kod `Point` , *x* ve *y* koordinatlarını temsil eden özel veri nesnelerini içeren adlı bir sınıfı tanımlar. Bu veri nesnelerinin değiştirilmesi ve değerlerinin alınması gerekir. Bu program, böyle bir sınıf için yalnızca birkaç tasarımdan biridir; `GetX` ve ya da işlevlerinin kullanımı, `SetX` `GetY` `SetY` başka bir tasarıma sahiptir.

Sınıf türleri, sınıf türlerine işaretçiler veya sınıf türlerine yapılan başvurular döndüren işlevler, üye seçim işleçleri için sol işlenen olarak kullanılabilir. Aşağıdaki kod geçerlidir:

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

[Sonek ifadeleri](../cpp/postfix-expressions.md)<br/>
[C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[İşlev çağrısı](../c-language/function-call-c.md)
