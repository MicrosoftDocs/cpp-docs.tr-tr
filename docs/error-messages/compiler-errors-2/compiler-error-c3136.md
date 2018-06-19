---
title: Derleyici Hatası C3136 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3136
dev_langs:
- C++
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f892c7f3d1ca7bf2aebf3ecfe7574182b544fd01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248857"
---
# <a name="compiler-error-c3136"></a>Derleyici Hatası C3136
'arabirimi': COM arabirimi yalnızca başka bir COM arabirimden devralan, 'arabirim' COM arabirimi değil  
  
 İçin uygulanan bir arabirim bir [arabirimi özniteliği](../../windows/interface-attributes.md) COM arabirimi olmayan bir arabirimden devralan. COM arabirimi sonuçta devraldığı `IUnknown`. Arabirim özniteliği tarafından öncesinde herhangi bir COM arabirimi arabirimidir.  
  
 Aşağıdaki örnek C3136 oluşturur:  
  
```  
// C3136.cpp  
#include "unknwn.h"  
  
__interface A   // C3136  
// try the following line instead  
// _interface A : IUnknown  
{  
   int a();  
};  
  
[object]  
__interface B : A  
{  
   int aa();  
};  
```