---
title: "C++ bildirim noktası | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: point of declaration
ms.assetid: 92ea8707-80cb-497c-b479-f907b8401859
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8a528bdeaa401aaab7d9287b0e9dd5aace2c93b1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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