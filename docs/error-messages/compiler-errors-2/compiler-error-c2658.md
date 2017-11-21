---
title: "Derleyici Hatası C2658 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2658
dev_langs: C++
helpviewer_keywords: C2658
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 252c543b8ba4dfc470bc1641a3d91c3dfc06177d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2658"></a>Derleyici Hatası C2658
'member': Birleşimdeki anonim struct/yeniden tanımlama  
  
 İki anonim yapılar veya birleşimler üye bildirimleri aynı tanımlayıcısı ile ancak farklı türleri içeriyor. Altında [/Za](../../build/reference/za-ze-disable-language-extensions.md), aynı tanımlayıcısı ve türe sahip üyeler için bu hatayı alırsınız.  
  
 Aşağıdaki örnek C2658 oluşturur:  
  
```  
// C2658.cpp  
// compile with: /c  
struct X {  
   union { // can be struct too  
      int i;  
   };  
   union {  
      int i;   // Under /Za, C2658  
      // int i not needed here because it is defined in the first union  
   };  
};  
  
struct Z {  
   union {  
      char *i;  
   };  
  
   union {  
      void *i;   // C2658 redefinition of 'i'  
      // try the following line instead  
      // void *ii;  
   };  
};  
```