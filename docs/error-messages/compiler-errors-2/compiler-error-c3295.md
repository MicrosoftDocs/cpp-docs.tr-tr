---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3295'
title: Derleyici hatası C3295
ms.date: 11/04/2016
f1_keywords:
- C3295
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
ms.openlocfilehash: 55fab24088690f5d5bb92da0cc55442bcebeed01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144631"
---
# <a name="compiler-error-c3295"></a>Derleyici hatası C3295

' #pragma pragma ' yalnızca genel veya ad alanı kapsamında kullanılabilir

Bazı pragmalar bir işlevde kullanılamaz.  Daha fazla bilgi için bkz. [pragma yönergeleri ve __pragma anahtar sözcüğü](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3295 oluşturur.

```cpp
// C3295.cpp
int main() {
   #pragma managed   // C3295
}
```
