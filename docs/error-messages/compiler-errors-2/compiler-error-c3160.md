---
title: Derleyici Hatası C3160 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3160
dev_langs:
- C++
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 670dd386be82b4356262cb59442d36fb1d6f646b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3160"></a>Derleyici Hatası C3160
'işaretçi': yönetilen veri üyesi ya da WinRT sınıfı bu türe sahip olamaz  
  
 İç atık toplama işaretçileri iç yönetilen ya da WinRT sınıfı işaret edebilir. Tüm nesne işaretçileri yavaş çalışır ve atık toplayıcı tarafından özel olarak işlenmesi gerektiği için bir sınıfın üyeleri olarak yönetilen iç işaretçiler bildiremezsiniz.  
  
 Aşağıdaki örnek C3160 oluşturur:  
  
```  
// C3160.cpp  
// compile with: /clr  
ref struct A {  
   // cannot create interior pointers inside a class  
   interior_ptr<int> pg;   // C3160  
   int g;   // OK  
   int* pg2;   // OK  
};  
  
int main() {  
   interior_ptr<int> pg2;   // OK  
}  
```  
