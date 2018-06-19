---
title: Derleyici Hatası C3373 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3373
dev_langs:
- C++
helpviewer_keywords:
- C3373
ms.assetid: 6e7586c3-1a15-4773-ad20-f90090a400dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc83e45f302cd5ef00532d8aca59db714b938e23
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254504"
---
# <a name="compiler-error-c3373"></a>Derleyici Hatası C3373
öznitelik 'özniteliği' dışında bağımsız değişkenler üzerinde bir coclass'ı alır.  
  
 Bazı öznitelikler birden fazla C++ yapı ancak öznitelik bağımsız değişkenleri yalnızca bazı yapıları üzerinde izin verilmiyor olabilir uygulanabilir.  
  
 Aşağıdaki örnek C3373 oluşturur:  
  
```  
// C3373.cpp  
#include <windows.h>  
  
[module(name="MyModule")];  
  
[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]  
__interface IMyIface  
{  
   // arguments to source and restricted are not allowed when  
   // these attributes are applied to an interface  
   [source(IMyIface)] HRESULT f1();  
   [restricted(IMyIface)] HRESULT f2(); // C3373  
};  
  
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f) ]  
class CMyClass : public IMyIface {  
};  
  
int main() {  
}  
```