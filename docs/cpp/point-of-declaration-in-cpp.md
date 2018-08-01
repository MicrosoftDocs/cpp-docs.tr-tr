---
title: C++ bildirim noktası | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89f94cdee6be18436b3f39f840fb7880e5860adb
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408703"
---
# <a name="point-of-declaration-in-c"></a>C++ bildirim noktası
Kendi bildirimci hemen sonra ancak (isteğe bağlı) başlatıcısı önce bildirilmesi için bir ad olarak kabul edilir. (Bildirimciler hakkında daha fazla bilgi için bkz. [bildirimlerinin ve tanımlarının](declarations-and-definitions-cpp.md).)  
  
 Bu örneği göz önünde bulundurun:  
  
```cpp 
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 Bildirim noktası olsaydı *sonra* başlatma ve ardından yerel `dVar` 7.0, genel değişkeninin değerini başlatılan `dVar`. Ancak, bu durumda olmadığından `dVar` tanımsız bir değerle başlatılır.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Kapsam](../cpp/scope-visual-cpp.md)