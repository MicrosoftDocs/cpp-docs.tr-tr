---
title: Derleyici Hatası C2867 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2867
dev_langs:
- C++
helpviewer_keywords:
- C2867
ms.assetid: 63be26b2-d9ab-4f3d-a8b7-981ce3e4d6b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 404bc16c77a8d327230744bb4b679e6d13249f7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245149"
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