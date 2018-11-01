---
title: Derleyici Uyarısı (düzey 4) C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: 1b1fb72d68309a4bef56ccd844ad30d967bbadbd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552951"
---
# <a name="compiler-warning-level-4-c4130"></a>Derleyici Uyarısı (düzey 4) C4130

'operator': dize sabitinin adresi üzerinde mantıksal işlem

Bir dize sabitinin adresi ile işlecini kullanarak, beklenmeyen bir kod üretir.

Aşağıdaki örnek, C4130 oluşturur:

```
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

**Varsa** deyimi işaretçide depolanan değeri karşılaştırır `pc` "Hello" dizesi adresine ayrıldığı ayrı olarak dize kod her gerçekleştiğinde. **Varsa** deyimi işaret ettiği dizeyi karşılaştırın değil `pc` "Hello" dizesi ile.

Dizeleri karşılaştırmak için kullanın `strcmp` işlevi.