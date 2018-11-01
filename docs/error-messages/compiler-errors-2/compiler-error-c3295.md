---
title: Derleyici Hatası C3295
ms.date: 11/04/2016
f1_keywords:
- C3295
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
ms.openlocfilehash: 63739989d737527e3f136bb3aac2269eda6231c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601701"
---
# <a name="compiler-error-c3295"></a>Derleyici Hatası C3295

'#pragma pragma' yalnızca kullanılabilir genel kapsamda veya ad alanı kapsamında

Bazı pragmalar bir işlevde kullanılamaz.  Bkz: [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3295 oluşturur.

```
// C3295.cpp
int main() {
   #pragma managed   // C3295
}
```