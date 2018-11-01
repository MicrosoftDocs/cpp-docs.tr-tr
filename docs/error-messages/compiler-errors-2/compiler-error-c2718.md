---
title: Derleyici Hatası C2718
ms.date: 11/04/2016
f1_keywords:
- C2718
helpviewer_keywords:
- C2718
ms.assetid: 78cc71f8-c142-46fc-9aed-970635d74f0c
ms.openlocfilehash: 00ad8da46364cd4a48ebdfde8b4de960e4e015f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473014"
---
# <a name="compiler-error-c2718"></a>Derleyici Hatası C2718

'parameter': hizalanmasına __declspec(align('#')) ile gerçek parametre hizalanmayacak

[Hizalama](../../cpp/align-cpp.md) `__declspec` değiştiricisi işlevi parametrelere izin verilmiyor.

Aşağıdaki örnek, C2718 oluşturur:

```
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