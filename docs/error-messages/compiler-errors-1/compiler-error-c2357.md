---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2357'
title: Derleyici hatası C2357
ms.date: 11/04/2016
f1_keywords:
- C2357
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
ms.openlocfilehash: a58317fc4706d6385d3753a434c8e4fd80dc79b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276744"
---
# <a name="compiler-error-c2357"></a>Derleyici hatası C2357

' Identifier ': ' Type ' türünde bir işlev olmalıdır

Kodunuz, `atexit` derleyici tarafından dahili olarak belirtilen sürümle eşleşmeyen bir işlev sürümü bildiriyor. `atexit`Aşağıdaki gibi bildirin:

```
int __cdecl atexit(void (__cdecl *)());
```

Daha fazla bilgi için bkz. [init_seg](../../preprocessor/init-seg.md).

Aşağıdaki örnek C2357 oluşturur:

```cpp
// C2357.cpp
// compile with: /c
// C2357 expected
#pragma warning(disable : 4075)
// Uncomment the following line to resolve.
// int __cdecl myexit(void (__cdecl *)());
#pragma init_seg(".mine$m",myexit)
```
