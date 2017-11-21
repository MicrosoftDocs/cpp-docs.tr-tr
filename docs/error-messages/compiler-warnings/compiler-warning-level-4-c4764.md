---
title: "Derleyici Uyarısı (düzey 4) C4764 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4764
dev_langs: C++
helpviewer_keywords: C4764
ms.assetid: 7bd4296f-966b-484c-bf73-8dbc8e85b4a9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 25f04d579d5f34d78197beacc262df482029b5c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4764"></a>Derleyici Uyarısı (düzey 4) C4764
16 bayttan büyük catch nesnelere hizalanamıyor  
  
 16 ' büyük bir hizalama belirtildi, ancak işlev bir özel durum oluşturursa bazı platformlarda 16'den büyük bir hizalama yığın zorla.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4764 oluşturur:  
  
```  
// C4764.cpp  
// compile with: /W4 /EHsc  
// processor: x64 IPF  
#include <stdio.h>  
  
class A   
{  
public:  
    int x;  
};  
  
typedef __declspec(align(32)) A ALIGNEDA;  
  
int main()   
{  
    ALIGNEDA a;  
    try   
    {  
        a.x = 15;  
        throw a;  
    }  
    catch (ALIGNEDA b) // can’t align b to > 16 bytes  
    {  
        printf_s("%d\n", b.x);  
    }  
}   // C4764  
```