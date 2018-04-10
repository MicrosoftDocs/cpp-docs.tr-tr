---
title: Derleyici Hatası C2583 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2583
dev_langs:
- C++
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8199698332d74242ef2dff9e43e26835afc0311c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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