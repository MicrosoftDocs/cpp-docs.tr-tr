---
title: Derleyici Hatası C3463 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3463
dev_langs:
- C++
helpviewer_keywords:
- C3463
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff9b680fb034a113627bcaecae8ba3cfc442f45e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257527"
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