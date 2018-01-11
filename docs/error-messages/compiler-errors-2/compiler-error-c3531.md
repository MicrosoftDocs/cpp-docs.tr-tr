---
title: "Derleyici Hatası C3531 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3531
dev_langs: C++
helpviewer_keywords: C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c7c8158d798df3fb48c45194ff6a01a1cbf3ab4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3531"></a>Derleyici Hatası C3531
'simgesi': türü içeren 'auto' bir simge bir başlatıcı olmalıdır  
  
 Belirtilen değişken Başlatıcısı ifade yok.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Eşittir işareti sözdizimi değişkeni bildirirken kullanan basit bir atama gibi bir başlatıcı ifade belirtin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3531 çünkü verir değişkenleri `x1`, `y1, y2, y3`, ve `z2` başlatılmaz.  
  
```  
// C3531.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto x1;                  // C3531  
   auto y1, y2, y3;          // C3531  
   auto z1 = 1, z2, z3 = -1; // C3531  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)