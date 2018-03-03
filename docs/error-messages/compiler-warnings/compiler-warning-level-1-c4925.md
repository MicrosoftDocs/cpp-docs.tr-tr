---
title: "Derleyici Uyarısı (düzey 1) C4925 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4925
dev_langs:
- C++
helpviewer_keywords:
- C4925
ms.assetid: a4b206c0-016a-4f28-873a-bb8bb41bad50
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e686aeb361e238470776a9f762e7fa6d3bc65648
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4925"></a>Derleyici Uyarısı (düzey 1) C4925
'yöntemi': görüntüleme arabirimi yöntemi betikten çağrılamaz  
  
 Komut dosyası dili 'ın' parametresi bir VT_BYREF oluşturulamıyor, yalnızca 'out' parametreleri VT_BYREF oluşturabilirsiniz.  
  
 Bu uyarıyı çözmek için başka bir parametre (tanımı ve uygulama) bir işaretçi türü olmamasını yoludur.  
  
 Aşağıdaki örnek C4925 oluşturur:  
  
```  
// C4925.cpp  
// compile with: /LD /W1  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[ module(name="Test")];  
  
[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IDisp {  
   [id(9)] void f([in] int*);  
};  
  
[ coclass, uuid("00000000-0000-0000-0000-000000000002")  ]  
struct CDisp : IDisp {   // C4925  
   void f(int*) {}  
};  
```