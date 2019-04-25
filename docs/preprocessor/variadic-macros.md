---
title: Variadic Makrolar
ms.date: 11/04/2016
helpviewer_keywords:
- variadic macros [C++]
- __VA_ARGS__ variadic macro specifier
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
ms.openlocfilehash: da159ef979ccc38845064debebae55356bc9e9bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179575"
---
# <a name="variadic-macros"></a>Variadic Makrolar

Değişen sayıda bağımsız değişken içeren makrolar, değişken sayıda bağımsız değişken içeren işlev benzeri makrolardır.

## <a name="remarks"></a>Açıklamalar

Bağımsız değişken içeren makroları kullanmak için üç nokta değiştirme tanımlayıcısı yanı sıra bir Makro tanımında son biçimsel bağımsız değişken olarak belirtilebilir `__VA_ARGS__` tanımında, ek bağımsız değişkenleri eklemek için kullanılabilir.  `__VA_ARGS__` Tüm aralarındaki virgüller de dahil olmak üzere üç nokta eşleşmesi bağımsız değişkenleri ile değiştirilir.

C Standardı, makronun arkasından virgül gelen bir ifadeye çözümlenmemesini sağlamak için üç noktaya en az bir bağımsız değişkenin geçirilmesi gerektiğini belirtir.  Üç noktaya hiçbir bağımsız değişken geçirilmezse, Visual C++ uygulaması sondaki virgülü gizler.

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