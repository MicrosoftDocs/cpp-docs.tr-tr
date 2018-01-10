---
title: "Derleyici Hatası C3468 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3468
dev_langs: C++
helpviewer_keywords: C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3a5b81e6b8b8d1e3949aba2016950bcc64eef7e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3468"></a>Derleyici Hatası C3468
'type': yalnızca bir tür bir derlemeye iletebilirsiniz:  
  
 '`file`' bağımlılığı derleme değil  
  
 Yalnızca derlemedeki türleri iletilebilir.  
  
 Daha fazla bilgi için bkz: [tür iletme (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir modül oluşturur.  
  
```  
// C3468.cpp  
// compile with: /LN /clr  
public ref class R {};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3468 oluşturur.  
  
```  
// C3468_b.cpp  
// compile with: /clr /c  
#using "C3468.netmodule"  
[ assembly:TypeForwardedTo(R::typeid) ];   // C3468  
```