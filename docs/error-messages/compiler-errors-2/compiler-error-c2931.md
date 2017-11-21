---
title: "Derleyici Hatası C2931 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2931
dev_langs: C++
helpviewer_keywords: C2931
ms.assetid: 33430407-b149-4ba3-baf8-b0dae1ea3a5d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b8289508c84b24a5077be2160a7915900d3619a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2931"></a>Derleyici Hatası C2931
'class': türü sınıfı kimliği yeniden tanımlandı 'tanımlayıcısı' bir üye işlevi  
  
 Genel veya Şablon sınıfı başka bir sınıf bir üye işlevini kullanamazsınız.  
  
 Küme ayraçları yanlış eşleşirse bu hataya neden olabilir.  
  
 Aşağıdaki örnek C2931 oluşturur:  
  
```  
// C2931.cpp  
// compile with: /c  
template<class T>   
struct TC { };   
struct MyStruct {  
   void TC<int>();   // C2931  
};  
  
struct TC2 { };   
struct MyStruct2 {  
   void TC2();  
};  
```  
  
 Ayrıca C2931 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2931b.cpp  
// compile with: /clr /c  
generic<class T> ref struct GC {};  
struct MyStruct {  
   void GC<int>();   // C2931  
   void GC2();   // OK  
};  
```