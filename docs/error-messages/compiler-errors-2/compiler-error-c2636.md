---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2636'
title: Derleyici hatası C2636
ms.date: 11/04/2016
f1_keywords:
- C2636
helpviewer_keywords:
- C2636
ms.assetid: 379873ec-8d05-49f8-adf1-b067bc07bdb8
ms.openlocfilehash: 789da819b85435bfb54d0f88c6e6c1414f04b6f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208742"
---
# <a name="compiler-error-c2636"></a>Derleyici hatası C2636

' tanımlayıcı ': başvuru üyesine yönelik işaretçi geçersizdir

Başvuru üyesine yönelik bir işaretçi bildirildi.

Aşağıdaki örnek C2636 oluşturur:

```cpp
// C2636.cpp
struct S {};
int main() {
   int &S::*prs;   // C2636
   int S::*prs1;   // OK
   int *S::*prs2;   // OK
}
```
