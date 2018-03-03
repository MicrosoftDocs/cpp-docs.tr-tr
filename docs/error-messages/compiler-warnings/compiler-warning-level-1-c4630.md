---
title: "Derleyici Uyarısı (düzey 1) C4630 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4630
dev_langs:
- C++
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7d045903874649b98eb4b79237445e167b3a5e2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4630"></a>Derleyici Uyarısı (düzey 1) C4630
'simgesi': 'extern' depolama sınıfı tanımlayıcısı üye tanımı geçersiz  
  
 Veri üyesi veya üye fonksiyonu olarak tanımlanır `extern`. Tüm nesneler; ancak üyeleri dış, olamaz. Derleyici yoksayar `extern` anahtar sözcüğü. Aşağıdaki örnek C4630 oluşturur:  
  
```  
// C4630.cpp  
// compile with: /W1 /LD  
class A {  
   void func();  
};  
  
extern void A::func() {   // C4630, remove 'extern' to resolve  
}  
```