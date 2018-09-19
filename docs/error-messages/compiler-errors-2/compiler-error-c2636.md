---
title: Derleyici Hatası C2636 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2636
dev_langs:
- C++
helpviewer_keywords:
- C2636
ms.assetid: 379873ec-8d05-49f8-adf1-b067bc07bdb8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5eb89c6e2a555aa6f832018a69a9648e8e2953ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086401"
---
# <a name="compiler-error-c2636"></a>Derleyici Hatası C2636

'identifier': başvuru üyesine yönelik işaretçi geçersizdir

Bir başvuru üyesine yönelik bir işaretçi bildirildi.

Aşağıdaki örnek, C2636 oluşturur:

```
// C2636.cpp
struct S {};
int main() {
   int &S::*prs;   // C2636
   int S::*prs1;   // OK
   int *S::*prs2;   // OK
}
```