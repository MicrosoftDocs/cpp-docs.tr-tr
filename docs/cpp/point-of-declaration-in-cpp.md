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
ms.openlocfilehash: e42f43e6187e19df6e9c1111c0e92aa4b9929199
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="point-of-declaration-in-c"></a>C++ bildirim noktası
Kendi bildirimcisi hemen sonra ancak kendi (isteğe bağlı) Başlatıcı önce bildirilmesi için bir ad olarak kabul edilir. (Bildirimciler hakkında daha fazla bilgi için bkz: [bildirimler ve tanımlar](declarations-and-definitions-cpp.md).)  
  
 Bu örneği göz önünde bulundurun:  
  
```  
// point_of_declaration1.cpp  
// compile with: /W1   
double dVar = 7.0;  
int main()  
{  
   double dVar = dVar;   // C4700  
}  
```  
  
 Bildirim noktası olsaydı *sonra* başlatma sonra yerel `dVar` 7.0, genel değişkenin değerini başlatılmış `dVar`. Ancak, bu durumda, olmadığından `dVar` tanımlanmamış bir değere başlatılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kapsam](../cpp/scope-visual-cpp.md)