---
title: Derleyici Uyarısı (düzey 1) C4669 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4669
dev_langs:
- C++
helpviewer_keywords:
- C4669
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f96bcf40b1fbc989daceabc810d019d1bb9aa98
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060869"
---
# <a name="compiler-warning-level-1-c4669"></a>Derleyici Uyarısı (düzey 1) C4669

'cast': Güvenli olmayan dönüştürme: 'class' olan bir yönetilen veya WinRT türü nesne

Bir yayın, bir Windows çalışma zamanı veya yönetilen türü içeriyor. Derleyici, diğer bir işaretçi temelinde bir kopyasını gerçekleştirerek atama tamamlanır, ancak hiçbir diğer denetim sağlar. Bu uyarıyı çözmek için yönetilen üyeleri veya Windows çalışma zamanı türleri içeren sınıfları yapmayın.

Aşağıdaki örnek, C4669 oluşturur ve bu sorunun nasıl gösterir:

```
// C4669.cpp
// compile with: /clr /W1
ref struct A {
   int i;
   Object ^ pObj;   // remove the managed member to fix the warning
};

ref struct B {
   int j;
};

int main() {
   A ^ a = gcnew A;
   B ^ b = reinterpret_cast<B ^>(a);   // C4669
}
```