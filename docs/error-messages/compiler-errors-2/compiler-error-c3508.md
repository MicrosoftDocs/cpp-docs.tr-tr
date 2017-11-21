---
title: "Derleyici Hatası C3508 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3508
dev_langs: C++
helpviewer_keywords: C3508
ms.assetid: 16d08f89-2f32-44eb-9421-68acecddf49b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f30abe3356b9375883c9a0211d8eb63a5fd2d59a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3508"></a>Derleyici Hatası C3508
'type': geçerli bir Otomasyon türü değil  
  
 Geçersiz bir tür belirtildi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3508 oluşturur:  
  
```  
// C3508.cpp  
#define _ATL_DEBUG_QI  
  
#define WIN32_LEAN_AND_MEAN  
#define STRICT  
#ifndef _WIN32_WINNT  
#define _WIN32_WINNT 0x0400  
#endif  
  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
extern CComModule _Module;  
#include <atlcom.h>  
#include <atlctl.h>  
#include <atlstr.h>  
  
extern "C" int printf_s(const char*, ...);  
  
[module(name=oso)];  
  
union U  
// try the following two lines instead  
// [export]  
// struct U  
{  
   int i, j;  
};  
  
[dispinterface]  
__interface I  
{  
   [id(1)] HRESULT func(U* u);  
};  
  
[coclass]  
struct C : I  
{  
   HRESULT func(U*)   // C3508  
   {  
      return E_FAIL;  
   }  
};  
  
int main()  
{  
}  
```