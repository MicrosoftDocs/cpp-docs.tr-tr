---
title: 'Çağırma örneği: İşlev prototipi ve çağrı | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9f9ee05b55a0945d18e78dc67df5653c06c8a1bc
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404388"
---
# <a name="calling-example-function-prototype-and-call"></a>Çağırma Örneği: İşlev Prototipi ve Çağrı
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Aşağıdaki örnek, çeşitli çağırma kurallarını kullanarak bir işlevi çağırmak sonuçlarını gösterir.  
  
 Bu örnek, aşağıdaki işlev çatıyı üzerinde temel alır. Değiştirin `calltype` uygun çağırma kuralı.  
  
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
  
 Daha fazla bilgi için [çağırma örneği sonuçları](../cpp/results-of-calling-example.md).  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Çağırma Kuralları](../cpp/calling-conventions.md)