---
title: Derleyici Uyarısı (Düzey 3) C4267 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4267
dev_langs:
- C++
helpviewer_keywords:
- C4267
ms.assetid: 2fa2f13f-fa4f-47bb-ad8f-6cb19cfc91e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de75c4eb05002f638e6b665a39f2a35e114b0ab4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290169"
---
# <a name="compiler-warning-level-3-c4267"></a>Derleyici Uyarısı (Düzey 3) C4267
'var': 'yazmak için ', olası veri kaybını 'size_t' dönüştürme  
  
 Dönüştürme derleyici algılanan `size_t` daha küçük bir türü.  
  
 Bu uyarıyı çözmenin kullanmak `size_t` yerine `type`. Alternatif olarak, en az kadar büyük bir tam sayı türü kullanın `size_t`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4267 oluşturur.  
  
```  
// C4267.cpp  
// compile by using: cl /W4 C4267.cpp  
void Func1(short) {}  
void Func2(int) {}  
void Func3(long) {}  
void Func4(size_t) {}  
  
int main() {  
   size_t bufferSize = 10;  
   Func1(bufferSize);   // C4267 for all platforms  
   Func2(bufferSize);   // C4267 only for 64-bit platforms  
   Func3(bufferSize);   // C4267 only for 64-bit platforms  
   Func4(bufferSize);   // OK for all platforms  
}  
```