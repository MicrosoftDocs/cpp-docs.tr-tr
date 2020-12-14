---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4130'
title: Derleyici Uyarısı (düzey 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: e7096f471405b0b22bcb0a825dd9ccd0de4e3510
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261820"
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
