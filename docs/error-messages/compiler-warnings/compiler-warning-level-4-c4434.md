---
title: "Derleyici Uyarısı (düzey 4) C4434 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4434
dev_langs:
- C++
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9499d145263c3bbb1bd5aac948c6be9e4db48d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4434"></a>Derleyici Uyarısı (düzey 4) C4434
bir sınıf oluşturucu özel erişilebilirlik olmalıdır; özel erişimi değiştirme  
  
 C4434 derleyici statik Oluşturucu erişilebilirliğini değiştiğini gösterir. Bunlar yalnızca ortak dil çalışma zamanı tarafından çağrılacak yöneliktir gibi statik oluşturucular özel erişilebilirlik olması gerekir. Daha fazla bilgi için bkz: [statik oluşturucular](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4434 oluşturur.  
  
```  
// C4434.cpp  
// compile with: /W4 /c /clr  
public ref struct R {  
   static R(){}   // C4434  
};  
```