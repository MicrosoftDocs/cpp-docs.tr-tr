---
title: "Derleyici Hatası C2933 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2933
dev_langs: C++
helpviewer_keywords: C2933
ms.assetid: 394891e3-6b52-4b61-83d2-a1c5125d9bd5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3b1bf70a1dd6e4bef40521381ef28bc08cfb57a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2933"></a>Derleyici Hatası C2933
'class': türü sınıfı kimliği typedef üyesi 'tanımlayıcısı' olarak yeniden tanımlandı  
  
 Bir genel veya şablon sınıf olarak kullanarak bir `typedef` üye.  
  
 Aşağıdaki örnek C2933 oluşturur:  
  
```  
// C2933.cpp  
// compile with: /c  
template<class T> struct TC { };   
struct MyStruct {  
   typedef int TC<int>;   // C2933  
};  
  
struct TC2 { };   
struct MyStruct2 {  
   typedef int TC2;  
};  
```  
  
 Ayrıca C2933 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2933b.cpp  
// compile with: /clr /c  
generic<class T> ref struct GC { };  
struct MyStruct {  
   typedef int GC<int>;   // C2933  
};  
  
ref struct GC2 { };  
struct MyStruct2 {  
   typedef int GC2;  
};  
```