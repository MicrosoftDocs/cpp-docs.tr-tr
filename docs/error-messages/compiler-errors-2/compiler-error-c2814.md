---
title: Derleyici Hatası C2814 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2814
dev_langs:
- C++
helpviewer_keywords:
- C2814
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75215a0df53606c8807cc275e86616c1ae8c6b42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2814"></a>Derleyici Hatası C2814
'member': yerel tür yönetilen veya WinRT içinde iç içe olamaz 'type' yazın  
  
## <a name="example"></a>Örnek  
 Yerel tür bir CLR veya WinRT türünde iç içe olamaz. Aşağıdaki örnek C2814 oluşturur ve nasıl düzeltileceği gösterir.  
  
```  
// C2814.cpp  
// compile with: /clr /c  
ref class A {  
   class B {};   // C2814  
   ref class C {};   // OK  
};  
```  
