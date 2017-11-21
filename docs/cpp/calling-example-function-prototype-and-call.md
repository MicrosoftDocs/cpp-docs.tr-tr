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
ms.openlocfilehash: 6076869ac21f5d934e06e6338215da7ed3e7f6dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Çağırma kuralları](../cpp/calling-conventions.md)