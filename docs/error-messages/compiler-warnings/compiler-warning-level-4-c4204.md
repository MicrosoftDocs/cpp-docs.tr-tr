---
title: "Derleyici Uyarısı (düzey 4) C4204 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4204
dev_langs: C++
helpviewer_keywords: C4204
ms.assetid: 298d2880-6737-448e-b711-15572d540200
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: defdacf0de90248e0cd91a4a5d12fdbec42a9320
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4204"></a>Derleyici Uyarısı (düzey 4) C4204
kullanılan standart olmayan uzantısı: Sabit olmayan toplama Başlatıcı  
  
 Microsoft Uzantıları (/Ze) ile toplama türleriyle (diziler, yapılar, birleşimler ve sınıfları) sabitleri olmayan değerleri başlatabilirsiniz.  
  
## <a name="example"></a>Örnek  
  
```  
// C4204.c  
// compile with: /W4  
int func1()  
{  
   return 0;  
}  
struct S1  
{  
   int i;  
};  
  
int main()  
{  
   struct S1 s1 = { func1() };   // C4204  
   return s1.i;  
}  
```  
  
 Bu tür başlatmaları ANSI Uyumluluğu altında geçersiz ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).