---
title: Derleyici Hatası C2362 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2362
dev_langs:
- C++
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53b0b77930acba6ecf2d0f3c6748ba52e9b28e0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33222182"
---
# <a name="compiler-error-c2362"></a>Derleyici Hatası C2362
'tanımlayıcısının' başlatma 'goto etiketle' atlandı  
  
 İle derleme yapılırken [/Za](../../build/reference/za-ze-disable-language-extensions.md), etikete atladıktan engeller tanıtıcı başlatılmış.  
  
 Bildirim değildir girildiği bir bloğunda içine sürece bir başlatıcı bildirimiyle geçmiş atlama olamaz veya değişken zaten başlatıldı.  
  
 Aşağıdaki örnek C2326 oluşturur:  
  
```  
// C2362.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   int i = 1;      // C2362, initialization skipped  
label1:;  
}  
```  
  
 Olası çözüm:  
  
```  
// C2362b.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   {  
      int j = 1;   // OK, this block is never entered  
   }  
label1:;  
}  
```