---
description: 'Daha fazla bilgi edinin: değişken bağımsız sayıda makro'
title: Değişen sayıda makro
ms.date: 10/17/2019
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
ms.openlocfilehash: 74bf5b68696499ea8b1d88722d8a9e55f2ecab2d
ms.sourcegitcommit: 48b897797b3132ae934b1d191e3870c3c2466335
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97514588"
---
# <a name="variadic-macros"></a>Değişen sayıda makro

Değişen sayıda bağımsız değişken içeren makrolar, değişken sayıda bağımsız değişken içeren işlev benzeri makrolardır.

## <a name="remarks"></a>Açıklamalar

Değişen sayıda sayıda makro kullanmak için, üç nokta bir makro tanımında son biçimsel bağımsız değişken olarak belirtilebilir ve `__VA_ARGS__` ek bağımsız değişkenleri eklemek için tanımda değiştirme tanımlayıcısı kullanılabilir.  `__VA_ARGS__` , aralarında virgül de dahil olmak üzere üç nokta ile eşleşen tüm bağımsız değişkenlerle değiştirilmiştir.

C standardı, makronun sonunda virgül olan bir ifadeye çözümlenmemesini sağlamak için üç nokta için en az bir bağımsız değişken geçirilmesi gerektiğini belirtir. Geleneksel Microsoft C++ uygulamasının, üç nokta işaretine hiçbir bağımsız değişken geçirilmezse sondaki virgül bastırır. [`/Zc:preprocessor`](../build/reference/zc-preprocessor.md)Derleyici seçeneği ayarlandığında, sondaki virgül gizlenemedi.

## <a name="example"></a>Örnek

```cpp
// variadic_macros.cpp
#include <stdio.h>
#define EMPTY

#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }
#define CHECK3(...) { printf(__VA_ARGS__); }
#define MACRO(s, ...) printf(s, __VA_ARGS__)

int main() {
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print

    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");

    // always invokes printf in the macro
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");

    MACRO("hello, world\n");

    MACRO("error\n", EMPTY); // would cause error C2059, except VC++
                             // suppresses the trailing comma
}
```

```Output
here are some varargs1(1)
here are some varargs2(4)
here are some varargs3(5)
hello, world
error
```

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar (C/C++)](../preprocessor/macros-c-cpp.md)
