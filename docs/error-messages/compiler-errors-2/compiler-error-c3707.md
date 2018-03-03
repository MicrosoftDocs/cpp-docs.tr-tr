---
title: "Derleyici Hatası C3707 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3707
dev_langs:
- C++
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3c61c23c093106267b4854109a8cfeb699bda78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3707"></a>Derleyici Hatası C3707
'function': görüntüleme arabirimi yöntemi DISPID olması gerekir  
  
 Kullanırsanız, bir `dispinterface` yöntemi atamanız gerekir, bir `dispid`. Bu hatayı düzeltmek için Ata bir `dispid` için `dispinterface` yöntemi, örneğin, uncommenting tarafından `id` örnek yönteminde özniteliği. Öznitelikleri daha fazla bilgi için bkz: [görüntüleme arabirimi](../../windows/dispinterface.md) ve [kimliği](../../windows/id.md).  
  
 Aşağıdaki örnek C3707 oluşturur:  
  
```  
// C3707.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(name="xx")];  
[dispinterface]  
__interface IEvents : IDispatch  
{  
   HRESULT event1([in] int i);   // C3707  
   // try the following line instead  
   // [id(1)] HRESULT event1([in] int i);  
};  
  
int main() {  
}  
```