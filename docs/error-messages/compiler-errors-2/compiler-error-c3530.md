---
title: "Derleyici Hatası C3530 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3530
dev_langs: C++
helpviewer_keywords: C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d66e76fc3e44a037f52aa6e217fae848f1338d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3530"></a>Derleyici Hatası C3530
'auto' tüm diğer tür-belirteci ile birlikte kullanılamaz  
  
 Tür belirteci ile birlikte kullanılan `auto` anahtar sözcüğü.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Tür belirteci kullanan bir değişken bildirimi kullanmayın `auto` anahtar sözcüğü.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3530 çünkü verir değişkeni `x` ikisi ile bildirilmiş `auto` anahtar sözcüğü ve türü `int`, ve örnek ile derlendiğinden **/Zc:auto**.  
  
```  
// C3530.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto int x;   // C3530  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Auto anahtar sözcüğü](../../cpp/auto-keyword.md)