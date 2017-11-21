---
title: "Derleyici Hatası C3718 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3718
dev_langs: C++
helpviewer_keywords: C3718
ms.assetid: 346b5205-c44d-49d3-b66a-96417d3d6986
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 87a41b0937935038cf4f6d30d2abc1f47afef7c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3718"></a>Derleyici Hatası C3718
yalnızca 'event' alıcı sınıfının üye işlevini bağlamında çağırabilir  
  
 `event` Alıcı sınıfından yalnızca çağrılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3718 oluşturur:  
  
```  
// C3718.cpp  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="test")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I  
{  
    HRESULT f();  
};  
  
[event_source(com), coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct E  
{  
    __event __interface I;  
};  
  
[event_receiver(com)]  
struct R  
{  
    void b()  
    {  
        printf_s("B::bar()\n");   
    }  
  
    void HookAndRun(E* pE)  
    {  
        __hook(&I::f, pE->GetUnknown(), &R::b);  
        __raise pE->f();  
    }  
};  
  
int main()  
{  
    CComObject<E>* pE;  
    CComObject<E>::CreateInstance(&pE);  
  
    __hook(&I::f, pE->GetUnknown(), &R::b, &r);   // C3718  
    __raise pE->f();  
    // try the following lines instead  
    // R r;  
    // r.HookAndRun(pE);  
}  
```