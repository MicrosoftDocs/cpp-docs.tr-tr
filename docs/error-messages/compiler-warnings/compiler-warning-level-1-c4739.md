---
title: Derleyici Uyarısı (düzey 1) C4739 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4739
dev_langs:
- C++
helpviewer_keywords:
- C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c90acdbc8ab32522e8e7cfac079547caaf84398d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281911"
---
# <a name="compiler-warning-level-1-c4739"></a>Derleyici Uyarısı (düzey 1) C4739
değişken 'var' referansı, depolama alanı aşıyor  
  
 Bir değişkene bir değer atandı, ancak değişkeni boyutundan daha büyük bir değerdir. Bellek değişkenin bellek konumuna yazılır ve veri kaybı mümkündür.  
  
 Bu uyarıyı çözmek için yalnızca bir değer büyüklüğü değeri barındırabilecek bir değişkene atayın.  
  
 Aşağıdaki örnek C4739 oluşturur:  
  
```  
// C4739.cpp  
// compile with: /RTCs /Zi /W1 /c  
char *pc;  
int main() {  
   char c;  
   *(int *)&c = 1;   // C4739  
  
   // OK  
   *(char *)&c = 1;  
}  
```