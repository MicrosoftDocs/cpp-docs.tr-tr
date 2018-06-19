---
title: Derleyici Hatası C3530 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3530
dev_langs:
- C++
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6514d655ab813ae21ecb440415f87bce63f3591
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253524"
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