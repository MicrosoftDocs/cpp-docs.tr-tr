---
title: __ptr32, __ptr64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5746c8f54a51e24bad23dcb66f6648266e2e4b56
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704821"
---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64

**Microsoft özel**

`__ptr32` yerel bir işaretçi bir 32 bit sistemdeki temsil ederken `__ptr64` yerel bir işaretçi bir 64-bit sistemde temsil eder.

Aşağıdaki örnek, bu işaretçi türleri bildirme gösterilmektedir:

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

 İle bir işaretçi bir 32 bit sistemde bildirilen `__ptr64` 32-bit işaretçi kesilir. İle bir işaretçi bir 64-bit sistemde bildirilen `__ptr32` bir 64-bit işaretçi yüklenen.

> [!NOTE]
> Kullanamazsınız `__ptr32` veya `__ptr64` ile derleme yapılırken **/CLR: pure**. Derleyici Hatası C2472 yoksa, oluşturulur. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek bildirme ve işaretçileri ile tahsis gösterilmektedir `__ptr32` ve `__ptr64` anahtar sözcükler.

```cpp
#include <cstdlib>
#include <iostream>

int main()
{
    using namespace std;

    int * __ptr32 p32;
    int * __ptr64 p64;

    p32 = (int * __ptr32)malloc(4);
    *p32 = 32;
    cout << *p32 << endl;

    p64 = (int * __ptr64)malloc(4);
    *p64 = 64;
    cout << *p64 << endl;
}
```

```Output
32
64
```

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

- [Temel Türler](../cpp/fundamental-types-cpp.md)