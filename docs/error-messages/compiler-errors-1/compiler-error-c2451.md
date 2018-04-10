---
title: Derleyici Hatası C2451 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2451
dev_langs:
- C++
helpviewer_keywords:
- C2451
ms.assetid: a64c93a5-ab8d-4d39-ae57-9ee7ef803036
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb51691832736287b9a288108e3a3f4ae040e10d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2451"></a>Derleyici Hatası C2451
Koşullu ifade ' type' türünde geçersiz  
  
 Koşullu ifade tamsayı türü için değerlendirir.  
  
 Aşağıdaki örnek C2451 oluşturur:  
  
```  
// C2451.cpp  
class B {};  
  
int main () {  
   B b1;  
   int i = 0;  
   if (b1)   // C2451  
   // try the following line instead  
   // if (i)  
      ;  
}  
```