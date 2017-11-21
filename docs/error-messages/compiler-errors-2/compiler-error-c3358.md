---
title: "Derleyici Hatası C3358 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3358
dev_langs: C++
helpviewer_keywords: C3358
ms.assetid: 180b93df-e78f-441a-91fb-1594c681f7f0
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0a4e062fd21577836ae1b56d2d0e277b162d9451
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3358"></a>Derleyici Hatası C3358
'simgesi': sembol bulunamadı  
  
 Gerekli simgesi bulunamadı.  
  
 Aşağıdaki örnek C3358 oluşturur:  
  
```  
// C3358.cpp  
#define __ATLEVENT_H__ 1   // remove this line to resolve the error  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[event_receiver(com)]  
struct A   // C3358  
{  
   void func();  
};  
  
int main()  
{  
}  
```