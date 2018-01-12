---
title: "Derleyici Hatası C2810 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2810
dev_langs: C++
helpviewer_keywords: C2810
ms.assetid: f63e8f24-d7f6-42ac-904f-72ff49592ba6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4c1f79d519ad3ebec635525f97347b7a83aac56b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2810"></a>Derleyici Hatası C2810
'arabirimi': Arabirim yalnızca başka bir arabirimden devralan  
  
 Bir [arabirimi](../../cpp/interface.md) yalnızca başka bir arabirimden devralan ve bir sınıf veya yapı devralmayan.  
  
 Aşağıdaki örnek C2810 oluşturur:  
  
```  
// C2810.cpp  
#include <unknwn.h>  
class CBase1 {  
public:  
  HRESULT mf1();  
  int  m_i;  
};  
  
[object, uuid="40719E20-EF37-11D1-978D-0000F805D73B"]  
__interface IDerived : public CBase1 {  // C2810  
// try the following line instead  
// __interface IDerived {  
   HRESULT mf2(void *a);  
};  
  
struct CBase2 {  
   HRESULT mf1(int a, char *b);  
   HRESULT mf2();  
};  
```