---
title: Derleyici Uyarısı (düzey 1) C4677 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4677
dev_langs:
- C++
helpviewer_keywords:
- C4677
ms.assetid: a8d656a1-e2ff-4f8b-9028-201765131026
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3511ad3100bf695cec5df97703b39e5926c71c11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281700"
---
# <a name="compiler-warning-level-1-c4677"></a>Derleyici Uyarısı (düzey 1) C4677
'function': İmza özel olmayan üye olarak içeren derleme özel türü 'private_type'  
  
 Derleme dışına ortak erişilebilirlik olan bir türü derleme dışına özel erişimi olan bir türünü kullanır. Genel derleme türüne başvuran bir bileşen türü üyesine ya da derleme özel türü başvuru üyelerine kullanmanız mümkün olmaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4677 oluşturur.  
  
```  
// C4677.cpp  
// compile with: /clr /c /W1  
delegate void TestDel();  
public delegate void TestDel2();  
  
public ref class MyClass {  
public:  
   static event TestDel^ MyClass_Event;   // C4677  
   static event TestDel2^ MyClass_Event2;   // OK  
};  
```