---
description: 'Hakkında daha fazla bilgi edinin: __ptr32 __ptr64'
title: __ptr32, __ptr64
ms.date: 10/09/2018
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
- __ptr32
- __ptr64
- _ptr32
- _ptr64
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
ms.openlocfilehash: 3393cdfddf08ba2ae5366cacae8554faa7c4a50c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299039"
---
# <a name="__ptr32-__ptr64"></a>__ptr32, __ptr64

**Microsoft'a Özgü**

**`__ptr32`** 32 bitlik bir sistemde yerel bir işaretçiyi temsil ederken, **`__ptr64`** 64 bit sistemde yerel bir işaretçiyi temsil eder.

Aşağıdaki örnek, bu işaretçi türlerinin her birinin nasıl bildirilemeyeceğini göstermektedir:

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

32 bitlik bir sistemde, ile belirtilen bir işaretçi **`__ptr64`** 32 bitlik bir işaretçiye kesilir. 64 bitlik bir sistemde, ile belirtilen bir işaretçi **`__ptr32`** 64 bit işaretçiye zorlanır.

> [!NOTE]
> **`__ptr32`** **`__ptr64`** **/Clr: Pure** ile derleme yaparken veya kullanamazsınız. Aksi halde, derleyici hatası C2472 oluşturulur. **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Önceki sürümlerle uyumluluk için, **_ptr32** ve **_ptr64** , için eş anlamlılardır **`__ptr32`** ve **`__ptr64`** [/za \( Disable dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) gibi derleyici seçeneği belirtilmiştir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, **`__ptr32`** ve anahtar sözcükleriyle işaretçilerin nasıl bildirilemeyeceğini ve ayrılacağını gösterir **`__ptr64`** .

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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Yerleşik türler](../cpp/fundamental-types-cpp.md)
