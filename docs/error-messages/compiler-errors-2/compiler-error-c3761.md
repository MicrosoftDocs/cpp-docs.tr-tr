---
title: Derleyici Hatası C3761 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3761
dev_langs:
- C++
helpviewer_keywords:
- C3761
ms.assetid: 0c16f093-7a78-4838-b90b-0c67ef6e9270
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 327c1526b59f84064c9ba0e444341d8795fb98a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268872"
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