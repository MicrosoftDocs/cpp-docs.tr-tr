---
title: "Derleyici Hatası C2638 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2638
dev_langs: C++
helpviewer_keywords: C2638
ms.assetid: 9d4275e8-406d-455e-afee-3a37799230e0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f5eb7d56c715ade00d8aa4ca5c9e41a73441561
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2638"></a>Derleyici Hatası C2638
'tanımlayıcısı': değiştiricisi geçersiz işaretçiden üyeye üzerinde __based  
  
 `__based` Değiştiricisi üye işaretçileri için kullanılamaz.  
  
 Aşağıdaki örnek C2638 oluşturur:  
  
```  
// C2638.cpp  
void *a;  
  
class C {  
public:  
   int i;  
   int j;  
   int func();  
};  
int __based (a) C::* cpi = &C::i;  // C2638  
int (__based (a) C::* cpf)() = &C::func; // c2638  
```