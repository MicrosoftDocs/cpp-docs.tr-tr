---
title: Derleyici Hatası C3733 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3733
dev_langs:
- C++
helpviewer_keywords:
- C3733
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7d5531bf9eb7352f1866bc0800734a78261b585
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266636"
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