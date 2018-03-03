---
title: "Derleyici Hatası C3530 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3530
dev_langs:
- C++
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a71820e6303c67e3d247c7da6dddc184e5cb41a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)