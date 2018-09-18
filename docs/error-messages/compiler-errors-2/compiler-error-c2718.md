---
title: Derleyici Hatası C2718 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2718
dev_langs:
- C++
helpviewer_keywords:
- C2718
ms.assetid: 78cc71f8-c142-46fc-9aed-970635d74f0c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: facbee46968cf76e6709bceff4432ba289aed3cd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045776"
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