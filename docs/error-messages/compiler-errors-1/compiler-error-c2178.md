---
title: "Derleyici Hatası C2178 | Microsoft Docs"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2178
dev_langs:
- C++
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b4e61c9148db2a6eccdef308e30ada976a917833
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2178"></a>Derleyici Hatası C2178  
  
'*tanımlayıcısı*'ile bildirilemez'*belirticisi*' tanımlayıcısı  
  
A `mutable` belirleyici bir bildiriminde kullanıldı, ancak belirleyici bu bağlamda izin verilmiyor.  
  
`mutable` Belirticisi yalnızca sınıf veri üyesi adlarına uygulanabilir ve bildirilen adlarına uygulanamaz `const` veya `static`ve üyeleri başvurmak için uygulanamaz.  
  
## <a name="example"></a>Örnek  
  
Aşağıdaki örnek C2178 nasıl oluşabilir ve bu sorunun nasıl gösterir.  
  
```  
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```  
