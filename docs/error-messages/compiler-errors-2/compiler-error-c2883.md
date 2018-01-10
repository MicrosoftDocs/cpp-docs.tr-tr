---
title: "Derleyici Hatası C2883 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2883
dev_langs: C++
helpviewer_keywords: C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b2a52236d3c017307ad44c6103f1770422239881
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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