---
title: Derleyici Hatası C2648 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2648
dev_langs:
- C++
helpviewer_keywords:
- C2648
ms.assetid: ce338337-9154-4f85-bb61-b05fdbfad75d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1d5a6fcf5fa4a1a8451a2d5be9ea188a8d58bd1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230896"
---
# <a name="compiler-error-c2648"></a>Derleyici Hatası C2648
'tanımlayıcısı': statik üye varsayılan parametre gerektirdiği şekilde üyesi kullanın  
  
 Statik olmayan üye varsayılan parametre olarak kullanılır.  
  
 Aşağıdaki örnek C2648 oluşturur:  
  
```  
// C2648.cpp  
// compile with: /c  
class C {  
public:  
   int i;  
   static int j;  
   void func1( int i = i );  // C2648  i is not static  
   void func2( int i = j );  // OK  
};  
```