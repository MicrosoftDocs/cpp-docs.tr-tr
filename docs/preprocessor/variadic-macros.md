---
title: Değişen sayıda makro
ms.date: 08/29/2019
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
ms.openlocfilehash: 171ea797adc1e407a8b7ef0592508653f758df64
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216524"
---
# <a name="variadic-macros"></a>Değişen sayıda makro

Değişen sayıda bağımsız değişken içeren makrolar, değişken sayıda bağımsız değişken içeren işlev benzeri makrolardır.

## <a name="remarks"></a>Açıklamalar

Değişen sayıda sayıda makro kullanmak için, üç nokta bir makro tanımında son biçimsel bağımsız değişken olarak belirtilebilir ve ek bağımsız değişkenleri eklemek için tanımda `__VA_ARGS__` değiştirme tanımlayıcısı kullanılabilir.  `__VA_ARGS__`, aralarında virgül de dahil olmak üzere üç nokta ile eşleşen tüm bağımsız değişkenlerle değiştirilmiştir.

C standardı, makronun sondaki virgülden sonra bir ifadeye çözümlenmemesini sağlamak için en az bir bağımsız değişkenin üç noktaya geçirilmesi gerektiğini belirtir. Geleneksel Microsoft C++ uygulama, üç nokta için bir bağımsız değişken geçirilmezse sondaki virgülden geçer.

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
