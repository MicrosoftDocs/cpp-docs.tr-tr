---
title: "Derleyici Hatası C2678 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2678
dev_langs: C++
helpviewer_keywords: C2678
ms.assetid: 1f0a4e26-b429-44f5-9f94-cb66441220c8
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d743ba1fbd9b65a7aa8b0f83634848e16b56c407
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2678"></a>Derleyici Hatası C2678
İkili 'işleci': 'type' türündeki sol işleneni aldığı hiçbir işleci tanımlanan (veya kabul edilebilir bir dönüştürme yok)  
  
 İşleç kullanmak için belirtilen tür için aşırı yükleme veya işleci tanımlandığı bir türe dönüştürme tanımlayın.  
  
## <a name="example"></a>Örnek  
 C2678 const tam sol işleneni ancak işleci const olmayan bağımsız değişken yapılacak tanımlı ortaya çıkabilir.  
  
 Aşağıdaki örnek C2678 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2678a.cpp  
// Compile by using: cl /EHsc /W4 C2678a.cpp  
struct Combo {  
   int number;  
   char letter;  
};  
  
inline Combo& operator+=(Combo& lhs, int rhs) {  
   lhs.number += rhs;  
   return lhs;  
}  
  
int main() {  
   Combo const combo1{ 42, 'X' };  
   Combo combo2{ 13, 'Z' };  
  
   combo1 += 6; // C2678  
   combo2 += 9; // OK - operator+= matches non-const Combo  
}  
```  
  
## <a name="example"></a>Örnek  
 Yerel üyesi üye işlevi çağrılmadan önce değil sabitlerseniz C2678 da oluşabilir.  
  
 Aşağıdaki örnek C2678 oluşturur ve nasıl düzeltileceği gösterir.  
  
```  
// C2678.cpp  
// compile with: /clr /c  
struct S { int _a; };  
  
ref class C {  
public:  
   void M( S param ) {  
      test = param;   // C2678  
  
      // OK  
      pin_ptr<S> ptest = &test;  
      *ptest = param;  
   }  
   S test;  
};  
```  
