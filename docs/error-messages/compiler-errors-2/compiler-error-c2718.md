---
title: Derleyici hatası C2718
ms.date: 11/04/2016
f1_keywords:
- C2718
helpviewer_keywords:
- C2718
ms.assetid: 78cc71f8-c142-46fc-9aed-970635d74f0c
ms.openlocfilehash: ecfb68856e63eaf3f60e93a79bac17c66d1af1fc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760523"
---
# <a name="compiler-error-c2718"></a>Derleyici hatası C2718

' Parameter ': __declspec (align (' # ')) ile gerçek parametre hizalanmayacak

[Hizalama](../../cpp/align-cpp.md) `__declspec` değiştiricisine işlev parametrelerinde izin verilmez.

Aşağıdaki örnek C2718 oluşturur:

```cpp
// C2718.cpp
typedef struct __declspec(align(32)) AlignedStruct  {
   int i;
} AlignedStruct;

void f2(int i, ...);

void f4() {
   AlignedStruct as;

   f2(0, as);   // C2718, actual parameter is aligned
}
```
