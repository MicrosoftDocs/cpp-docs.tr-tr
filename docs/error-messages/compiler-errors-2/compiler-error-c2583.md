---
title: Derleyici Hatası C2583 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2583
dev_langs:
- C++
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae9ef120d3dba9bc3c337d02aac302fce85f3905
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2583"></a>Derleyici Hatası C2583
'tanımlayıcısı': ' const/volatile' 'this' işaretçisini oluşturucular/için Yıkıcılar geçersiz  
  
 Oluşturucunun ya da yıkıcı bildirilmiş `const` veya `volatile`. Bu duruma izin verilmez.  
  
 Aşağıdaki örnek C2583 oluşturur:  
  
```  
// C2583.cpp  
// compile with: /c  
class A {  
public:  
   int i;  
   A() const;   // C2583  
  
   // try the following line instead  
   // A();  
};  
```