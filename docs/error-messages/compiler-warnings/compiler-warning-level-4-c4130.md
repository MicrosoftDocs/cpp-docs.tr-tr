---
title: Derleyici Uyarısı (düzey 4) C4130 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4130
dev_langs:
- C++
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21d73595e41c4c83eda61fa749c9f2dc72bb14bc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038106"
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