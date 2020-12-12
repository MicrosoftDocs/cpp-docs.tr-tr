---
description: 'Daha fazla bilgi edinin: açık tür dönüştürme Işleci: ()'
title: 'Açık Tür Dönüştürme İşleci: ()'
ms.date: 11/04/2016
helpviewer_keywords:
- explicit data type conversion operator
- conversions [C++], explicit
- operators [C++], explicit type conversion
- data type conversion [C++], explicit
- type conversion [C++], explicit conversions
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
ms.openlocfilehash: cb2a1ff742b71edf2f298512a55ab37dd3d37f77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273390"
---
# <a name="explicit-type-conversion-operator-"></a>Açık Tür Dönüştürme İşleci: ()

C++, işlev çağrısı sözdizimine benzer bir sözdizimi kullanarak açık tür dönüştürme sağlar.

## <a name="syntax"></a>Syntax

```
simple-type-name ( expression-list )
```

## <a name="remarks"></a>Açıklamalar

Bir *basit-tür adı* ve ardından ayraç içine alınmış bir *liste* , belirtilen ifadeleri kullanarak belirtilen türde bir nesne oluşturur. Aşağıdaki örnekte, int türüne yapılan açık tür dönüştürme gösterilmektedir:

```cpp
int i = int( d );
```

Aşağıdaki örnekte bir sınıfı gösterilmektedir `Point` .

## <a name="example"></a>Örnek

```cpp
// expre_Explicit_Type_Conversion_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class Point
{
public:
    // Define default constructor.
    Point() { _x = _y = 0; }
    // Define another constructor.
    Point( int X, int Y ) { _x = X; _y = Y; }

    // Define "accessor" functions as
    // reference types.
    unsigned& x() { return _x; }
    unsigned& y() { return _y; }
    void Show()   { cout << "x = " << _x << ", "
                         << "y = " << _y << "\n"; }
private:
    unsigned _x;
    unsigned _y;
};

int main()
{
    Point Point1, Point2;

    // Assign Point1 the explicit conversion
    //  of ( 10, 10 ).
    Point1 = Point( 10, 10 );

    // Use x() as an l-value by assigning an explicit
    //  conversion of 20 to type unsigned.
    Point1.x() = unsigned( 20 );
    Point1.Show();

    // Assign Point2 the default Point object.
    Point2 = Point();
    Point2.Show();
}
```

## <a name="output"></a>Çıktı

```Output
x = 20, y = 10
x = 0, y = 0
```

Yukarıdaki örnekte sabitler kullanılarak yapılan açık tür dönüştürme gösterilse de, aynı teknik bu dönüştürmeleri nesneler üzerinde gerçekleştirmek için de kullanılabilir. Aşağıdaki kod parçası bunu gösterir:

```cpp
int i = 7;
float d;

d = float( i );
```

Açık tür dönüştürmeleri, "atama" sözdizimi kullanılarak da belirtilebilir. Atama sözdizimi kullanılarak yeniden yazılan yukarıdaki örnek şöyle olur:

```cpp
d = (float)i;
```

Hem atama hem de işlev stili dönüştürmelerin sonuçları, tek değerlerden dönüştürme gerçekleştirilirken aynı olur. Bununla birlikte, işlev stili sözdiziminde dönüştürme için birden fazla bağımsız değişken belirtebilirsiniz. Bu fark, kullanıcı tanımlı türler için önemlidir. Bir `Point` sınıfını ve dönüştürme işlemlerini göz önünde bulundurun:

```cpp
struct Point
{
    Point( short x, short y ) { _x = x; _y = y; }
    ...
    short _x, _y;
};
...
Point pt = Point( 3, 10 );
```

İşlev stili dönüştürme kullanan önceki örnek, iki değerin ( *x* için bir ve *y* için) Kullanıcı tanımlı türe nasıl dönüştürüleceğini gösterir `Point` .

> [!CAUTION]
> C++ derleyicisinin yerleşik tür denetimini geçersiz kıldıkları için açık tür dönüştürmelerini dikkatlice kullanın.

[Atama](../cpp/cast-operator-parens.md) gösterimi *basit tür adı* olmayan türlere Dönüştürmelere (örneğin, işaretçi veya başvuru türleri) sahip olmak için kullanılmalıdır. *Basit tür adı* ile ifade edilebilir türlere dönüştürme, herhangi bir biçimde yazılabilir.

Atamalar içindeki tür tanımı geçersiz.

## <a name="see-also"></a>Ayrıca bkz.

[Sonek Ifadeleri](../cpp/postfix-expressions.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
