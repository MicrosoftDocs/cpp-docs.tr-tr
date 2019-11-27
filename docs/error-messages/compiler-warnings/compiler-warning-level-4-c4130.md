---
title: Derleyici Uyarısı (düzey 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: b55594608eccc5d1e5e764bffb73ecb3787af1e4
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541592"
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

**IF** ifadesinde, işaretçi kodda her gerçekleştiğinde ayrı olarak ayrılan "Hello" dizesinin adresine `pc` İşaretçisinde depolanan değeri karşılaştırır. **IF** ifadesinde işaret eden dize, "Hello" dizesiyle `pc` ile karşılaştırmaz.

Dizeleri karşılaştırmak için `strcmp` işlevini kullanın.