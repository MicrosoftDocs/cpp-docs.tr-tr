---
title: Derleyici Hatası C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: d761dfde26cce9c99ccd4c3e6fd86ae1d6e16ddc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351098"
---
# <a name="compiler-error-c2015"></a>Derleyici Hatası C2015

çok fazla karakter sabiti

Bir karakter sabiti, ikiden fazla karakter içeriyor. , Bir karakter standart karakter sabitlerinin ve iki karakter uzunluğunda karakter sabitlerinin sınırdır.

Örneğin, \t kaçış dizisi için tek bir karakter dönüştürülür.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2015 oluşturur:

```
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

## <a name="example"></a>Örnek

C2015, bir Microsoft uzantısı tam sayılara dönüştürülür karakter sabitleri kullanırken da meydana gelebilir.  Aşağıdaki örnek, C2015 oluşturur:

```
// C2015b.cpp
#include <stdio.h>

int main()
{
    int a = 'abcde';   // C2015

    int b = 'a';   // 'a' = ascii 0x61
    printf_s("%x\n", b);
}
```