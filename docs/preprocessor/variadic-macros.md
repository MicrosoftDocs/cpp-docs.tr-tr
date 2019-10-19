---
title: Değişen sayıda makro
ms.date: 10/17/2019
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
ms.openlocfilehash: de4d3a7f03f613cb058e564664f01837df23aefb
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72587890"
---
# <a name="variadic-macros"></a>Değişen sayıda makro

Değişen sayıda bağımsız değişken içeren makrolar, değişken sayıda bağımsız değişken içeren işlev benzeri makrolardır.

## <a name="remarks"></a>Açıklamalar

Değişen sayıda sayıda makro kullanmak için, üç nokta bir makro tanımında son biçimsel bağımsız değişken olarak belirtilebilir ve ek bağımsız değişkenleri eklemek için `__VA_ARGS__` değiştirme tanımlayıcısı tanımda kullanılabilir.  `__VA_ARGS__`, aralarında virgül de dahil olmak üzere üç nokta ile eşleşen tüm bağımsız değişkenlerle değiştirilmiştir.

C standardı, makronun sondaki virgülden sonra bir ifadeye çözümlenmemesini sağlamak için en az bir bağımsız değişkenin üç noktaya geçirilmesi gerektiğini belirtir. Geleneksel Microsoft C++ uygulama, üç nokta için bir bağımsız değişken geçirilmezse sondaki virgülden geçer. @No__t_0 derleyici seçeneği ayarlandığında, sondaki virgül görüntülenmez.

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
