---
title: "Derleyici Hatası C2955 | Microsoft Docs"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2955
dev_langs: C++
helpviewer_keywords: C2955
ms.assetid: 77709fb6-d69b-46fd-a62f-e8564563d01b
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: af3f53545aa70e738f14c902a7a75afc48275b57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2955"></a>Derleyici Hatası C2955
'tanımlayıcısı': sınıf şablonunu kullanın veya diğer genel gerektirir şablon veya genel bağımsız değişken listesi  
  
 Bir şablonu veya genel bağımsız değişken listesi olmadan bir tanımlayıcı olarak bir sınıf şablonu ya da sınıf genel kullanamazsınız.  
  
 Daha fazla bilgi için bkz: [sınıf şablonları](../../cpp/class-templates.md).  
  
 Aşağıdaki örnek C2955 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2955.cpp  
// compile with: /c  
template<class T>   
class X {};  
  
X x1;   // C2955  
X<int> x2;   // OK - this is how to fix it.  
```  
  
 C2955 da bir sınıf şablonunda bildirilen bir işlev için bir satır sonu tanımı çalışırken oluşabilir:  
  
```  
// C2955_b.cpp  
// compile with: /c  
template <class T>  
class CT {  
public:  
   void CTFunc();  
   void CTFunc2();  
};  
  
void CT::CTFunc() {}   // C2955  
  
// OK - this is how to fix it  
template <class T>  
void CT<T>::CTFunc2() {}  
  
```  
  
 Ayrıca C2955 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2955_c.cpp  
// compile with: /clr  
generic <class T>   
ref struct GC {   
   T t;  
};  
  
int main() {  
   GC^ g;   // C2955  
   GC <int>^ g;  
}  
```

## <a name="example"></a>Örnek
**Visual Studio 2017 ve üzeri:** şablonu (örneğin varsayılan şablon bağımsız değişken veya kapsamında tür olmayan şablon parametresi) bir şablon parametre listesinde göründüğünde derleyici doğru eksik şablon bağımsız değişken listeleri tanılar. Aşağıdaki kod, Visual Studio 2015'te derler ancak Visual Studio 2017 hata üretir.

```
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias 
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```
