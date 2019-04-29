---
title: Derleyici Hatası C2371
ms.date: 11/04/2016
f1_keywords:
- C2371
helpviewer_keywords:
- C2371
ms.assetid: d383993d-05ef-4e35-8129-3b58a6f7b7b7
ms.openlocfilehash: 6fe9e85451d973ddd3983a935a9d1349c2699efb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338980"
---
# <a name="compiler-error-c2371"></a>Derleyici Hatası C2371

'identifier': yeniden tanımlama; temel türler farklı

Tanımlayıcı zaten bildirildi.

Aşağıdaki örnek, C2371 oluşturur:

```
// C2371.cpp
int main() {
   int i;
   float i;   // C2371, redefinition
   float f;   // OK
}
```