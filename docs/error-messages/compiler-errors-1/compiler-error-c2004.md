---
title: "Derleyici Hatası C2004 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2004
dev_langs: C++
helpviewer_keywords: C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 754f0099ac0b69eebbc98a34f7f6206591c75925
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2004"></a>Derleyici Hatası C2004
Beklenen 'defined(id)'  
  
 Tanımlayıcı önişlemci anahtar sözcüğü parantez içinde yer almalıdır.  
  
 Bu hata için Visual Studio .NET 2003 yapıldığı derleyici uyumluluğu iş sonucunda da oluşturulabilir: eksik parantez içine önişlemci yönergesi. Önişlemci yönergesi kapatma parantezi yoksa, derleyici bir hata oluşturur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2004 oluşturur:  
  
```  
// C2004.cpp  
// compile with: /DDEBUG  
#include <stdio.h>  
  
int main()   
{  
    #if defined(DEBUG   // C2004  
        printf_s("DEBUG defined\n");  
    #endif  
}  
```  
  
## <a name="example"></a>Örnek  
 Olası çözüm:  
  
```  
// C2004b.cpp  
// compile with: /DDEBUG  
#include <stdio.h>  
  
int main()   
{  
    #if defined(DEBUG)  
        printf_s("DEBUG defined\n");  
    #endif  
}  
```