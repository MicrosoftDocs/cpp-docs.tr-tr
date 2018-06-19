---
title: Derleyici Uyarısı (düzey 4) C4100 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4100
dev_langs:
- C++
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d3cf831590af2e1f2f7cd13d93c9d13ba217e11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292811"
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