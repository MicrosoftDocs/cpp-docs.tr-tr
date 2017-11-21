---
title: "Derleyici Hatası C3117 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3117
dev_langs: C++
helpviewer_keywords: C3117
ms.assetid: dceee392-d4c7-4599-b75e-7aaac7c36fdd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7f95c5e8073f896c42eebd273ff5923778847a56
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3117"></a>Derleyici Hatası C3117
'%$S': Arabirim yalnızca bir temel sınıfı olabilir  
  
 Birden çok taban sınıflardan devralan bir arabirim bildirildi.  
  
 Aşağıdaki örnek C3117 oluşturur:  
  
```  
// C3117.cpp  
#include <windows.h>  
  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface I1  
{  
};  
  
[ object, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface I2  
{  
};  
  
[ object, uuid("00000000-0000-0000-0000-000000000003") ]  
__interface I3 : I1, I2  
{   // C3117  
};  
```