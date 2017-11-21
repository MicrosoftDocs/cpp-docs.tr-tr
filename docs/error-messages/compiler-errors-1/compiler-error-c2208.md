---
title: "Derleyici Hatası C2208 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2208
dev_langs: C++
helpviewer_keywords: C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1fd07ee02251a3ea1ef7b0da1bc8e27685eb42ff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2208"></a>Derleyici Hatası C2208
'type': Bu türü kullanılarak tanımlanmış bir üye yok  
  
 Bir tür adı çözümlenirken bir tanımlayıcı, bir toplama bildiriminde olmakla birlikte derleyici üyesi bildiremezsiniz.  
  
 Aşağıdaki örnek C2208 oluşturur:  
  
```  
// C2208.cpp  
class C {  
   C;   // C2208  
   C(){}   // OK  
};  
```