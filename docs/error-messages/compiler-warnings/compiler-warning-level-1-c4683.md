---
title: Derleyici Uyarısı (düzey 1) C4683 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4683
dev_langs:
- C++
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 418bf25d565c616d5bc4aaf58361c4f28df298ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4683"></a>Derleyici Uyarısı (düzey 1) C4683
**'**   
 ***işlev* ': olay kaynağı olan bir 'out'-parametre; alıştırma dikkatli birden çok olay işleyicileri takma**  
  
 Birden fazla olay iç havuz bir COM Olay kaynağına dinliyor ise, out parametresi değeri göz ardı.  
  
 Bellek sızıntısı şu durumda oluşacağını unutmayın:  
  
1.  Bir yöntem dahili olarak, örneğin bir BSTR ayrılan out parametresi varsa *.  
  
2.  Olay birden fazla işleyici varsa (bir çok noktaya yayın olayıdır)  
  
 Out parametresi birden fazla işleyici tarafından ayarlanmış, ancak çağrı siteye yalnızca son işleyici tarafından döndürülen olduğunu sızıntısı nedeni.  
  
 Aşağıdaki örnek C4683 oluşturur:  
  
```  
// C4683.cpp  
// compile with: /W1 /LD  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[ module(name="xx") ];  
  
[ object ]  
__interface I {  
   HRESULT f([out] int* pi);  
   // try the following line instead  
   // HRESULT f(int* pi);  
};  
  
[ coclass, event_source(com) ]  
struct E {  
   __event __interface I;   // C4683  
};  
```