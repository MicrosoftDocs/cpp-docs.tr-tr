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
ms.workload: cplusplus
ms.openlocfilehash: 78b243a8fcda85c708d43aeee5586aa88a6596fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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