---
title: Derleyici Hatası C2594 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2594
dev_langs:
- C++
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b1de853b8992d3c02eb94c0b050d72539fc3282
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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