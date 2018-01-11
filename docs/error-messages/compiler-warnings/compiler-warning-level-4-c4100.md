---
title: "Derleyici Uyarısı (düzey 4) C4100 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4100
dev_langs: C++
helpviewer_keywords: C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 72236ee0c100388906689121a0936daf23c58e89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4100"></a>Derleyici Uyarısı (düzey 4) C4100
'tanımlayıcısı': başvurulmayan biçimsel parametresi  
  
 Biçimsel parametresi, işlev gövdesine başvurulmuyor. Başvurulmayan parametre yoksayılır.  
  
 C4100 ayrıca verilen kodu üzerinde bir yıkıcı çağırdığında bir aksi başvurulmayan ilkel tür parametresi.  Visual C++ derleyicisi kısıtlamasıdır.  
  
 Aşağıdaki örnek C4100 oluşturur:  
  
```  
// C4100.cpp  
// compile with: /W4  
void func(int i) {   // C4100, delete the unreferenced parameter to  
                     //resolve the warning  
   // i;   // or, add a reference like this  
}  
  
int main()  
{  
   func(1);  
}  
```