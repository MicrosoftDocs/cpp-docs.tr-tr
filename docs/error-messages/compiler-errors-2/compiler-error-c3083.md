---
title: Derleyici Hatası C3083 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3083
dev_langs:
- C++
helpviewer_keywords:
- C3083
ms.assetid: 05ff791d-52bb-41eb-9511-3ef89d7f4710
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7e0a60fbe976e8ab511efce8fc46d59e473958a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253052"
---
# <a name="compiler-error-c3083"></a>Derleyici Hatası C3083
'function': simgenin sol tarafındaki bir '::' bir tür olmalıdır  
  
 Bir işlevin yanlış çağrıldı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3083 oluşturur.  
  
```  
// C3083.cpp  
// compile with: /c  
struct N {  
   ~N();  
};  
  
struct N1 {  
   ~N1();  
};  
  
N::N::~N() {}   // C3083  
N1::~N1() {}   // OK  
```