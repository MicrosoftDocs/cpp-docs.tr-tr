---
title: "Derleyici Uyarısı (düzey 1) C4312 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4312
dev_langs: C++
helpviewer_keywords: C4312
ms.assetid: 541906ed-4f62-4bcb-947f-cf9ae7411bcb
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0a4e6fa46fe9b84b138fffedf206d08ffbb30790
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4312"></a>Derleyici Uyarısı (düzey 1) C4312
'operation' : 'type1' öğesinden daha büyük boyutlu 'type2' öğesine dönüştürme  
  
 Bu uyarı 32-bit atama 64-bit işaretçi türü için örneğin, 32 bitlik bir değer atama denemesi algılar `int` veya `long` 64-bit işaretçisi.  
  
 Bu, güvenli olmayan bir dönüştürme bile 32 bit cinsinden oturum uzantısı oluştuğunda uyan işaretçi değerleri için olabilir. Negatif bir 32 bit tamsayı bir 64-bit işaretçi türü atanırsa, oturum uzantısı tamsayı değerinden farklı bir bellek adresi başvurmak işaretçi değeri neden olur.  
  
 Bu uyarı yalnızca 64-bit derleme hedefler için görüntülenir. Daha fazla bilgi için bkz: [kullanarak işaretçileri için kuralları](http://msdn.microsoft.com/library/windows/desktop/aa384242).  
  
 64-bit hedefler için derlenmiştir olduğunda aşağıdaki kod örneğinde C4312 oluşturur:  
  
```  
// C4312.cpp  
// compile by using: cl /W1 /LD C4312.cpp  
void* f(int i) {  
   return (void*)i;   // C4312 for 64-bit targets  
}  
  
void* f2(__int64 i) {  
   return (void*)i;   // OK  
}  
```