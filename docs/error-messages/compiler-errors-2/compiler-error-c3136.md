---
title: "Derleyici Hatası C3136 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3136
dev_langs: C++
helpviewer_keywords: C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9e6a8e3c958c6c1293b20451f632910001ef24f2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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