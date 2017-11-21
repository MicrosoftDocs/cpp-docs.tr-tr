---
title: "Derleyici Uyarısı (Düzey 3) C4414 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4414
dev_langs: C++
helpviewer_keywords: C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 90644170953976d0fb661f1491b59915d5dd3667
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4414"></a>Derleyici Uyarısı (Düzey 3) C4414
'function': yakınında dönüştürülür kısa atlama işlevi  
  
 Kısa atlar hangi sınırlı bir aralıkta bir adres için yönerge dallar compact yönerge oluşturur. Yönerge atlama ve hedef adres, işlev tanımının arasındaki mesafeyi temsil eden kısa bir uzaklık içerir. Bir işlev bağlama sırasında kısa bir uzaklık ulaşılabilir aralık dışında taşınacak işlevi neden taşınmış veya konu için bağlama zamanı iyileştirmeler olabilir. Derleyici yakın veya uzak olarak jmp yönerge gerektirir atlama için özel bir kaydı oluşturmanız gerekir. Derleyici dönüştürme yapılan.  
  
 Örneğin, aşağıdaki kod C4414 oluşturur:  
  
```  
// C4414.cpp  
// compile with: /W3 /c  
// processor: x86  
int DoParityEven();  
int DoParityOdd();  
unsigned char global;  
int __declspec(naked) DoParityEither()  
{  
   __asm  
   {  
      test global,0  
      jpe SHORT DoParityEven  // C4414  
      jmp SHORT DoParityOdd   // C4414  
   }  
}  
```