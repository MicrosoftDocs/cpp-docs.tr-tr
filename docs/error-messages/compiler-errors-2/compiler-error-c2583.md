---
title: "Derleyici Hatası C2583 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2583
dev_langs: C++
helpviewer_keywords: C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 924a370a59fff0e118b76e52e17d44b3b2268103
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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