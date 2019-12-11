---
title: Derleyici Uyarısı (düzey 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: 3bc632bf641fa3944cfd21dc405590c803498d80
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991573"
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
