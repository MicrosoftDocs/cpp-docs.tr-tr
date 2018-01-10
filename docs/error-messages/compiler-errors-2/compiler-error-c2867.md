---
title: "Derleyici Hatası C2867 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2867
dev_langs: C++
helpviewer_keywords: C2867
ms.assetid: 63be26b2-d9ab-4f3d-a8b7-981ce3e4d6b9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d49fdc3a9e78e6b3903d8ea0015e03f8a1a24e65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2867"></a>Derleyici Hatası C2867
'tanımlayıcısı': bir ad değil  
  
 A `using` yönergesi için bir ad alanı dışında bir şey uygulanır.  
  
 Aşağıdaki örnek C2867 oluşturur:  
  
```  
// C2867.cpp  
// compile with: /c  
namespace N {  
   class X {};  
}  
using namespace N::X;   // C2867  
```