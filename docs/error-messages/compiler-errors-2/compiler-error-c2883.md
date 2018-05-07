---
title: Derleyici Hatası C2883 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2883
dev_langs:
- C++
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc3119db27127521f5078a5753bb82c82da381ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2883"></a>Derleyici Hatası C2883
'name': 'using bildirimi tarafından sunulan tanımlayıcısı' çakışıyor işlevi bildirimi  
  
 Bir işlev birden çok kez tanımlayın çalışıldı. İlk tanım içeren bir ad yapılan bir `using` bildirimi. İkinci bir yerel tanımı oluştu.  
  
 Aşağıdaki örnek C2883 oluşturur:  
  
```  
// C2883.cpp  
namespace A {  
   void z(int);  
}  
  
int main() {  
   using A::z;  
   void z(int);   // C2883  z is already defined  
}  
```