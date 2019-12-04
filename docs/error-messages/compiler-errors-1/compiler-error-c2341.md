---
title: Derleyici hatası C2341
ms.date: 11/04/2016
f1_keywords:
- C2341
helpviewer_keywords:
- C2341
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
ms.openlocfilehash: 6147ce954c6d21d86f76d1fd8ec6b8a1a5070a12
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760055"
---
# <a name="compiler-error-c2341"></a>Derleyici hatası C2341

' bölüm adı ': segmentin kullanılmadan önce #pragma data_seg, code_seg veya bölüm kullanılarak tanımlanması gerekir

[Allocate](../../cpp/allocate.md) deyimleri, henüz [code_seg](../../preprocessor/code-seg.md), [data_seg](../../preprocessor/data-seg.md)veya [bölüm](../../preprocessor/section.md) pragmaları tarafından tanımlanmayan bir kesime başvurur.

Aşağıdaki örnek C2341 oluşturur:

```cpp
// C2341.cpp
// compile with: /c
__declspec(allocate(".test"))   // C2341
int j = 1;
```

Olası çözüm:

```cpp
// C2341b.cpp
// compile with: /c
#pragma data_seg(".test")
__declspec(allocate(".test"))
int j = 1;
```
