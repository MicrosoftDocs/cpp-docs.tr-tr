---
title: "Derleyici Uyarısı (Düzey 2) C4285 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4285
dev_langs: C++
helpviewer_keywords: C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0893334b46ed4b0790996482dd5625978705d3ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4285"></a>Derleyici Uyarısı (Düzey 2) C4285
'identifier::operator -> için' dönüş türü iç gösterimini kullanarak uyguladıysanız yinelemelidir  
  
 Belirtilen **-> () işleci** işlev türü için döndüremiyor, tanımlanan veya için bunu tanımlanmış türüne bir başvuru.  
  
 Aşağıdaki örnek C4285 oluşturur:  
  
```  
// C4285.cpp  
// compile with: /W2  
class C  
{  
public:  
    C operator->();   // C4285  
   // C& operator->();  C4285, also  
};  
  
int main()  
{  
}  
```