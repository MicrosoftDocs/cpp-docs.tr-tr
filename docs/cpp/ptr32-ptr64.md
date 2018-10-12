---
title: __ptr32, __ptr64 | Microsoft Docs
ms.custom: ''
ms.date: 10/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
- __ptr32
- __ptr64
- _ptr32
- _ptr64
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
ms.openlocfilehash: 50360ab6a163f70f4f950e44d963b9aa67dc04f4
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161651"
---
# <a name="ptr32-ptr64"></a>__ptr32, __ptr64

**Microsoft'a özgü**

**__ptr32** 32-bit sistemde yerel bir işaretçiyi temsil ederken **__ptr64** 64-bit sistemde yerel bir işaretçiyi temsil eder.

Aşağıdaki örnek, bu İşaretçi türlerinin her biri bildirmek gösterilmektedir:

```cpp
int * __ptr32 p32;
int * __ptr64 p64;
```

Bir işaretçi bir 32-bit sistemde bildirilen **__ptr64** 32 bit işaretçi kesilir. Bir işaretçi bir 64-bit sistemde bildirilen **__ptr32** 64-bit işaretçi durumunda bırakılması.

> [!NOTE]
> Kullanamazsınız **__ptr32** veya **__ptr64** ile derleme yaparken **/CLR: pure**. Aksi halde, derleyici hatası C2472 oluşturulur. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Önceki sürümlerle uyumluluk için **_ptr32** ve **_ptr64** için eş anlamlı sözcükler olan **__ptr32** ve **__ptr64** sürece derleyici seçeneği [/Za \(dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md) belirtilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bildirmek ve işaretçilerle ayırmak gösterilmektedir **__ptr32** ve **__ptr64** anahtar sözcükleri.

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Temel Türler](../cpp/fundamental-types-cpp.md)