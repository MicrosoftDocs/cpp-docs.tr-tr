---
title: "Derleyici Hatası C3761 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3761
dev_langs: C++
helpviewer_keywords: C3761
ms.assetid: 0c16f093-7a78-4838-b90b-0c67ef6e9270
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a854ddbd481616e799b6c6df7b814d955faedce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3761"></a>Derleyici Hatası C3761
'function': 'retval' yalnızca bir işlevi son bağımsız değişken görünür  
  
 [Retval](../../windows/retval.md) özniteliği, listedeki son bağımsız değişken değil bir işlev bağımsız değişkeni üzerinde kullanıldı.  
  
 Aşağıdaki örnek C3761 oluşturur:  
  
```  
// C3761.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(name=test) ];  
  
[dispinterface]  
__interface I  
{  
   [id(1)] HRESULT func([out, retval] int* i, [in] int j);  
   // try the following line instead  
   // [id(1)] HRESULT func([in] int i, [out, retval] int* j);  
};  
  
[coclass]  
struct C : I {   // C3761  
   HRESULT func(int* i, int j)  
   // try the following line instead  
   // HRESULT func(int j, int* i)  
   {  
      return S_OK;  
   }  
};  
  
int main()  
{  
}  
```