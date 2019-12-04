---
title: Derleyici hatası C2636
ms.date: 11/04/2016
f1_keywords:
- C2636
helpviewer_keywords:
- C2636
ms.assetid: 379873ec-8d05-49f8-adf1-b067bc07bdb8
ms.openlocfilehash: f93998d717cbc3558bcab5045cc34c3f6a2c9a89
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737042"
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
