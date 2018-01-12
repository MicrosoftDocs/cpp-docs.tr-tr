---
title: "Derleyici Hatası C2594 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2594
dev_langs: C++
helpviewer_keywords: C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d4cca18672aad77e051ff4428dc115c53cd5ddad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2594"></a>Derleyici Hatası C2594
'işleci': 'type1' öğesinden 'type2' belirsiz dönüşümler  
  
 Dönüştürme yok *type1* için *type2* diğerinden daha doğrudan oluştu. Dönüştürme için iki olası çözümleri önerdiğimiz *type1* için *type2*. İlk seçenek doğrudan dönüştürme tanımlamaktır *type1* için *type2*, ve bir dizi dönüşümleri belirtmek için ikinci seçenek ise *type1* için  *type2*.  
  
 Aşağıdaki örnek C2594 oluşturur. Önerilen çözüm hata dönüşümleri dizisidir.:  
  
```  
// C2594.cpp  
// compile with: /c  
struct A{};  
struct I1 : A {};  
struct I2 : A {};  
struct D : I1, I2 {};  
  
A *f (D *p) {  
   return (A*) (p);    // C2594  
  
// try the following line instead  
// return static_cast<A *>(static_cast<I1 *>(p));  
}  
```