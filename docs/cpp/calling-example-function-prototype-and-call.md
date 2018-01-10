---
title: "Çağırma örneği: İşlev prototipi ve çağrı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: afdc7d91e11936ebfd1775477f8c684ae4ff6d62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="calling-example-function-prototype-and-call"></a>Çağırma Örneği: İşlev Prototipi ve Çağrı
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Aşağıdaki örnek, çeşitli çağırma kurallarını kullanarak bir işlev çağrısı yapma sonuçları gösterir.  
  
 Bu örnekte aşağıdaki işlevi çatıyı üzerinde temel alır. Değiştir `calltype` uygun çağırma kuralı.  
  
```  
void    calltype MyFunc( char c, short s, int i, double f );  
.  
.  
.  
void    MyFunc( char c, short s, int i, double f )  
    {  
    .  
    .  
    .  
    }  
.  
.  
.  
MyFunc ('x', 12, 8192, 2.7183);  
```  
  
 Daha fazla bilgi için bkz: [çağırma örneği sonuçları](../cpp/results-of-calling-example.md).  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma Kuralları](../cpp/calling-conventions.md)