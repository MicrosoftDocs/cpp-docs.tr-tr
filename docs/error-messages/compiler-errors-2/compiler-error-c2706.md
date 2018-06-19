---
title: Derleyici Hatası C2706 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2706
dev_langs:
- C++
helpviewer_keywords:
- C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92f64ddab93fb6815e3ff7a98ac39a842042bfeb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232652"
---
# <a name="compiler-error-c2706"></a>Derleyici Hatası C2706
eşleşen olmadan __except geçersiz \__try (eksik '}' içinde \__try blok?)  
  
 Derleme için bir kapanış ayracı bulamadı bir `__try` bloğu.  
  
 Aşağıdaki örnek C2706 oluşturur:  
  
```  
// C2706.cpp  
int main() {  
   __try {  
      void f();  
   // C2706  } missing here  
   __except(GetExceptionCode() == 0x0) {  
   }  
}  
```