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
ms.openlocfilehash: 050317be4c5f933ca9e08055a02555f5597c583c
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406539"
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