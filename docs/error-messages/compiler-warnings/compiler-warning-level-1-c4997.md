---
title: "Derleyici Uyarısı (düzey 1) C4997 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4997
dev_langs: C++
helpviewer_keywords: C4997
ms.assetid: d39678fd-0c1a-4104-8a45-9e3f20de0407
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cb9c3c0d2b48db5676c8510c75ef9e6bee42a160
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4997"></a>Derleyici Uyarısı (düzey 1) C4997
'class': COM arabirimi veya Sahte Arabirimi coclass'ı uygulamıyor  
  
 Bir sınıf ile işaretli [coclass](../../windows/coclass.md) özniteliği bir arabirimini uygulamaz.  
  
 Aşağıdaki örnek C4997 oluşturur:  
  
```  
// C4997.cpp  
// compile with: /WX  
// to resolve this C4997, uncomment all code  
#include <objbase.h>  
  
[ object ]  
__interface I {  
   HRESULT func();  
};  
  
[ coclass ]  
struct C /*: I*/ {  
   /*  
   HRESULT func() {  
      return S_OK;  
   }  
   */  
};   // C4997  
```