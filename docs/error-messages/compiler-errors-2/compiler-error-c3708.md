---
title: "Derleyici Hatası C3708 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3708
dev_langs: C++
helpviewer_keywords: C3708
ms.assetid: 45e71564-9c7f-437f-98d8-a735ce162ed0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8cc63e34c42f2c8d91c787530680d76e81192569
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3708"></a>Derleyici Hatası C3708
'arabirimi': 'anahtar sözcüğü'; yanlış kullanımı uyumlu olay kaynağı üyesi olması gerekir  
  
 Bir olay olarak bir arabirim bildirmek için olay bildirimi bir olay kaynağı olmalıdır.  
  
 Aşağıdaki örnek C3708 oluşturur:  
  
```  
// C3708.cpp  
// compile with: /c  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[ module(name="MyLibrary")];  
  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface I {  
   HRESULT func();  
};  
  
[ object, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface II {  
   HRESULT func();  
};  
  
__event __interface I;   // C3708  
  
// put the event in an event source  
[ coclass, event_source(com), uuid("00000000-0000-0000-0000-000000000003") ]  
struct E : II {  
   __event __interface II;  
};  
```