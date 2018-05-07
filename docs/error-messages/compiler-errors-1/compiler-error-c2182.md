---
title: Derleyici Hatası C2182 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2182
dev_langs:
- C++
helpviewer_keywords:
- C2182
ms.assetid: dfd8d47d-9606-496e-bd96-4bf41ba1f857
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72f72cddad59d4768029bc682181ce55e7537c44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2182"></a>Derleyici Hatası C2182
'tanımlayıcısı': 'void' türünün geçersiz kullanımı  
  
 Bir değişken türü bildirilmiş `void`.  
  
 Aşağıdaki örnek C2182 oluşturur:  
  
```  
// C2182.cpp  
// compile with: /c  
int main() {  
   int i = 10;  
   void &ir = i;   // C2182 cannot have a reference to type void  
   int &ir = i;   // OK  
}  
```