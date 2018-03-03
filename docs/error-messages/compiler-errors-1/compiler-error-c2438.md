---
title: "Derleyici Hatası C2438 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2438
dev_langs:
- C++
helpviewer_keywords:
- C2438
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dda1d429c785a5def5c2e596085e700370f37c60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2438"></a>Derleyici Hatası C2438
'tanımlayıcısı': statik sınıf veri Oluşturucusu aracılığıyla başlatılamıyor  
  
 Bir oluşturucu statik bir sınıf üyesi başlatmak için kullanılır. Statik üyeler sınıf bildiriminin dışında tanımında başlatılmalıdır.  
  
 Aşağıdaki örnek C2438 oluşturur:  
  
```  
// C2438.cpp  
struct X {  
   X(int i) : j(i) {}   // C2438  
   static int j;  
};  
  
int X::j;  
  
int main() {  
   X::j = 1;  
}  
```