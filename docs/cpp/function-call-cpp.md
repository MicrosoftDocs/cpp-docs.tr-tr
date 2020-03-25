---
title: İşlev Çağrısı (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, C++ functions
- functions [C++], calling
- operator overloading [C++], function calls
- function overloading [C++], function-call operator
- function calls, operator
- operators [C++], overloading
- operator overloading [C++], examples
- function call operator ()
ms.assetid: 5094254a-045b-46f7-8653-69bc91e80dce
ms.openlocfilehash: 6c7326b0f9c9592cb2b3be973a5ba1747a2015a0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179815"
---
# <a name="function-call-c"></a>İşlev Çağrısı (C++)

Parantez kullanılarak çağrılan işlev çağrısı işleci, ikili bir işleçtir.

## <a name="syntax"></a>Sözdizimi

```
primary-expression ( expression-list )
```

## <a name="remarks"></a>Açıklamalar

Bu bağlamda, ilk işlenen `primary-expression` ve muhtemelen boş bir bağımsız değişken listesi olan `expression-list`ikinci işlenendir. İşlev çağrısı işleci, birkaç parametre gerektiren işlemler için kullanılır. `expression-list`, tek bir işlenen yerine bir liste olduğundan bu işe yarar. İşlev çağrısı işleci, statik olmayan bir üye işlevi olmalıdır.

İşlev çağrısı işleci, aşırı yüklendiğinde işlevlerin çağrılma biçimini değiştirmez; bunun yerine, işlecin belirli bir sınıf türünden nesnelere uygulandığında nasıl yorumlanacağını değiştirir. Örneğin, aşağıdaki kod genellikle anlamsız olacaktır:

```cpp
Point pt;
pt( 3, 2 );
```

Ancak uygun bir aşırı yüklenmiş işlev çağrısı işleci verildiğinde, bu söz dizimi `x` koordinatı 3 birimlerinin ve `y` koordinat 2 birimlerinin kaymasını sağlamak için kullanılabilir. Aşağıdaki kod, bu tür bir tanımı göstermektedir:

```cpp
// function_call.cpp
class Point
{
public:
    Point() { _x = _y = 0; }
    Point &operator()( int dx, int dy )
        { _x += dx; _y += dy; return *this; }
private:
    int _x, _y;
};

int main()
{
   Point pt;
   pt( 3, 2 );
}
```

İşlev çağrısı işlecinin bir işlevin adına değil, bir nesnenin adına uygulandığını unutmayın.

İşlev çağrısı işlecini bir işlev işaretçisi (işlevin kendisi yerine) kullanarak da aşırı yükleyebilirsiniz.

```cpp
typedef void(*ptf)();
void func()
{
}
struct S
{
   operator ptf()
   {
      return func;
   }
};

int main()
{
   S s;
   s();//operates as s.operator ptf()()
}
```

## <a name="see-also"></a>Ayrıca bkz.

[İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)
