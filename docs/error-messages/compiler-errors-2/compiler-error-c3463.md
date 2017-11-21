---
title: "Derleyici Hatası C3463 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3463
dev_langs: C++
helpviewer_keywords: C3463
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2c5f79f76329277fa24e90eaa0ab32209cafe6c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3463"></a>Derleyici Hatası C3463
'type': 'Implements' özniteliğinde izin verilmiyor türü  
  
 Geçersiz bir tür geçirilmedi [uygulayan](../../windows/implements-cpp.md) özniteliği. Örneğin, bir arabirim geçirebilirsiniz `implements`, ancak bir işaretçi bir arabirim geçiremezsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3463 oluşturur.  
  
```  
// C3463.cpp  
// compile with: /c  
#include <windows.h>  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface X {};  
  
typedef X* PX;  
  
[ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=PX) ]   // C3463  
// try the following line instead  
// [ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=X) ]  
class CMyClass : public X {};  
```