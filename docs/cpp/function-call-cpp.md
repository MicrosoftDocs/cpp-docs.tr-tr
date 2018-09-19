---
title: İşlev çağrısı (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d583609a1013620384e7e938182403fb5c694fb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081407"
---
# <a name="function-call-c"></a>İşlev Çağrısı (C++)

Parantez kullanılarak çağrılan işlev çağrısı işleci, ikili bir işleçtir.

## <a name="syntax"></a>Sözdizimi

```
primary-expression ( expression-list )
```

## <a name="remarks"></a>Açıklamalar

Bu bağlamda `primary-expression` ilk işlenen, ve `expression-list`, büyük olasılıkla boş bağımsız değişken listesini ise ikinci işlenendir. İşlev çağrısı işleci, birkaç parametre gerektiren işlemler için kullanılır. Bunun çalışmasının nedeni `expression-list` tek bir işlenen yerine bir listedir. İşlev çağrısı işleci, statik olmayan bir üye işlevi olmalıdır.

İşlev çağrısı işleci, aşırı yüklendiğinde işlevlerin çağrılma biçimini değiştirmez; bunun yerine, işlecin belirli bir sınıf türünden nesnelere uygulandığında nasıl yorumlanacağını değiştirir. Örneğin, aşağıdaki kod genellikle anlamsız olacaktır:

```cpp
Point pt;
pt( 3, 2 );
```

Uygun aşırı yüklenmiş işlev çağrısı işleci göz önünde bulundurulduğunda, ancak bu sözdizimi kaydırmak için kullanılabilir `x` koordinatını 3 birim ve `y` koordinatını 2 birim. Aşağıdaki kod, bu tür bir tanımı göstermektedir:

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

Ayrıca, bir işlev (işlevin kendisi yerine) için bir işaretçi kullanarak işlev çağrısı işleci aşırı yüklenebilir.

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