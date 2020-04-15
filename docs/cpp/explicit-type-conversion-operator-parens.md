---
title: 'Açık Tür Dönüştürme İşleci: ()'
ms.date: 11/04/2016
helpviewer_keywords:
- explicit data type conversion operator
- conversions [C++], explicit
- operators [C++], explicit type conversion
- data type conversion [C++], explicit
- type conversion [C++], explicit conversions
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
ms.openlocfilehash: c168653a82b4d4c5023de1f76a1e6269625c74d8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354857"
---
# <a name="explicit-type-conversion-operator-"></a>Açık Tür Dönüştürme İşleci: ()

C++, işlev çağrısı sözdizimine benzer bir sözdizimi kullanarak açık tür dönüştürme sağlar.

## <a name="syntax"></a>Sözdizimi

```
simple-type-name ( expression-list )
```

## <a name="remarks"></a>Açıklamalar

Parantez içinde ekteki bir *ifade listesi* nin ardından gelen *basit bir tür adı,* belirtilen ifadeleri kullanarak belirtilen türden bir nesne yi kurar. Aşağıdaki örnekte, int türüne yapılan açık tür dönüştürme gösterilmektedir:

```cpp
int i = int( d );
```

Aşağıdaki örnekbir `Point` sınıf gösterir.

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

İşlev stili dönüştürmeyi kullanan önceki örnek, iki değerin (biri *x* için, diğeri *y*için) kullanıcı tanımlı türe `Point`nasıl dönüştürüldüğünü gösterir.

> [!CAUTION]
> C++ derleyicisinin yerleşik tür denetimini geçersiz kıldıkları için açık tür dönüştürmelerini dikkatlice kullanın.

[Döküm](../cpp/cast-operator-parens.md) gösterimi, basit tür *adı* olmayan türlere (örneğin işaretçi veya başvuru türleri) dönüşümler için kullanılmalıdır. Basit bir *tür adı* ile ifade edilebilir türlere dönüştürme her iki formda da yazılabilir.

Dökümler içindeki tür tanımı yasa dışıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Sonek İfadeleri](../cpp/postfix-expressions.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
