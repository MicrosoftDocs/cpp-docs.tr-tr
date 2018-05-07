---
title: Derleyici Uyarısı (düzey 4) C4510 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4510
dev_langs:
- C++
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b280a15381f53b6836b321e25717cbed19c7271
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4510"></a>Derleyici Uyarısı (düzey 4) C4510
'class': varsayılan oluşturucu oluşturulamadı  
  
 Derleyici belirtilen sınıfı için varsayılan bir oluşturucu oluşturamaz ve kullanıcı tanımlı bir oluşturucu yok oluşturuldu. Bu tür nesneler oluşturmak mümkün olmaz.  
  
 Varsayılan bir Oluşturucu Oluşturma derleyici önlemek bazı durumlar vardır dahil olmak üzere:  
  
-   Const veri üyesi.  
  
-   Bir başvuru veri üyesi.  
  
 Bu üyeler başlatır sınıfı için bir kullanıcı tarafından tanımlanan varsayılan oluşturucu oluşturmanız gerekir.  
  
 Aşağıdaki örnek C4510 oluşturur:  
  
```  
// C4510.cpp  
// compile with: /W4  
struct A {  
   const int i;  
   int &j;  
   A& operator=( const A& ); // C4510 expected  
   // uncomment the following line to resolve this C4510  
   // A(int ii, int &jj) : i(ii), j(jj) {}  
};   // C4510  
  
int main() {  
}  
```