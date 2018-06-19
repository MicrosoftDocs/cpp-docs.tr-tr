---
title: Derleyici Hatası C3340 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3340
dev_langs:
- C++
helpviewer_keywords:
- C3340
ms.assetid: 23b12298-b92a-4717-8380-f165c998cb8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc5c412f34c12bcfe890e71cdbe59bd6f8ee7a63
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33255129"
---
# <a name="compiler-error-c3340"></a>Derleyici Hatası C3340
'arabirimi': arabirim 'restricted' ve 'sınıfı' coclass ' varsayılan' olamaz  
  
 [Kısıtlı](../../windows/restricted.md) özniteliği ve [varsayılan](../../windows/default-cpp.md) özniteliği karşılıklı olarak birbirini dışlar.  
  
 Aşağıdaki örnek C3340 oluşturur:  
  
```  
// C3340.cpp  
#include <windows.h>  
[module(name="MyModule")];  
  
[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]  
__interface IMyIface  
{  
   HRESULT f1();  
};  
  
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f),  
default(IMyIface),  
source(IMyIface),restricted(IMyIface) ]  
class CmyClass // C3340  
{  
};  
  
int main()  
{  
}  
```