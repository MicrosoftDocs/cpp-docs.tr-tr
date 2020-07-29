---
title: Derleyici Uyarısı (düzey 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: 7b2fbccfd3b124220d6e310c01adace1d3e112c1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219969"
---
# <a name="compiler-warning-level-4-c4130"></a>Derleyici Uyarısı (düzey 4) C4130

' operator ': Dize sabitinin adresi üzerinde mantıksal işlem

Bir dize sabit değerinin adresiyle işleci kullanılması beklenmeyen bir kod üretir.

Aşağıdaki örnek C4130 oluşturur:

```cpp
// C4130.cpp
// compile with: /W4
int main()
{
   char *pc;
   pc = "Hello";
   if (pc == "Hello") // C4130
   {
   }
}
```

**`if`** İfade, İşaretçisinde depolanan değeri, `pc` dize kodda her gerçekleştiğinde ayrı olarak ayrılan "Hello" dizesinin adresine karşılaştırır. **`if`** İfade, işaret eden dizeyi `pc` "Hello" dizesiyle karşılaştırmaz.

Dizeleri karşılaştırmak için `strcmp` işlevini kullanın.
