---
title: "Derleyici Hatası C3733 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3733
dev_langs: C++
helpviewer_keywords: C3733
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dedd36afd3b0211148c61ee3279d77eb25273c50
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3733"></a>Derleyici Hatası C3733
'event': COM olay; belirtmek için yanlış sözdizimi '__interface' unuttunuz mu?  
  
 COM olayı için yanlış sözdizimi kullanıldı. Bu hatayı düzeltmek için olay türünü değiştirin veya COM olay kurallarına uygun sözdizimini düzeltin.  
  
 Aşağıdaki örnek C3733 oluşturur:  
  
```  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[coclass, event_source(com), // change 'com' to 'native' to resolve  
uuid("00000000-0000-0000-0000-000000000001")]  
class A  
{  
   __event void func();   // C3733  
};  
  
int main()  
{  
}  
```