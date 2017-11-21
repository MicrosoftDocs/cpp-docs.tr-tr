---
title: "Derleyici Uyarısı (düzey 4) C4127 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4127
dev_langs: C++
helpviewer_keywords: C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 711543436c39f00da9fa754cf8a60349b51ab84b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4127"></a>Derleyici Uyarısı (düzey 4) C4127
Koşullu ifade sabittir  
  
 Kontrol eden bir ifade bir `if` deyimi veya `while` döngü bir sabite değerlendirir. Ortak kullanılan deyimsel kullanımı, 1 gibi Önemsiz sabitleri nedeniyle veya `true` bir ifadede bir işlemin sonucunu olmadığı sürece uyarı tetiklemez. Varsa kontrol eden bir ifade bir `while` döngü bir sabit ortadaki döngüden çıkılıp olduğundan, değiştirmeyi düşünün `while` ile döngü bir `for` döngü. Başlatma, sonlandırma test atlayın ve döngü artışı bir `for` gibi sonsuz olmasını döngü neden döngü `while(1)`, ve gövdesinden döngü çıkabilirsiniz `for` deyimi.  
  
 Aşağıdaki örnek C4127 oluşturulur ve nasıl kullanılacağını gösterir iki yolunu gösterir bir uyarıyı önlemek döngü için:  
  
```  
// C4127.cpp  
// compile with: /W4  
#include <stdio.h>  
int main() {  
   if (1 == 1) {}   // C4127  
   while (42) { break; }   // C4127  
  
   // OK  
   for ( ; ; ) {  
      printf("test\n");  
      break;  
   }  
}  
```