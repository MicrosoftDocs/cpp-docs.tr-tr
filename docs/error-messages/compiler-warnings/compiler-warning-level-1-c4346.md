---
title: "Derleyici Uyarısı (düzey 1) C4346 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4346
dev_langs:
- C++
helpviewer_keywords:
- C4346
ms.assetid: 68ee562d-cca9-4a2a-9a1b-14ad1a1e7396
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e6d425004fcc4dc26271b2bb56dbeffccc46311
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4346"></a>Derleyici Uyarısı (düzey 1) C4346
'name': bağımlı adı bir tür değil  
  
 [Typename](../../cpp/typename.md) anahtar sözcüğü, bağımlı bir adı bir tür olarak kabul edilmesi için ise gereklidir. Aynı Visual C++'in tüm sürümlerinde çalışır kodu ekleyin `typename` bildirimine.  
  
 Aşağıdaki örnek C4346 oluşturur:  
  
```  
// C4346.cpp  
// compile with: /WX /LD  
template<class T>  
struct C {  
   T::X* x;   // C4346  
   // try the following line instead  
   // typename T::X* x;  
};  
```  
  
 Aşağıdaki örnekler diğer örnekleri gösterir nerede **typename** anahtar sözcüğü gereklidir:  
  
```  
// C4346b.cpp  
// compile with: /LD /W1  
template<class T>  
const typename T::X& f(typename T::Z* p);   // Required in both places  
  
template<class T, int N>  
struct L{};  
  
template<class T>  
struct M : public L<typename T::Type, T::Value>   
{   // required on type argument, not on non-type argument  
   typedef typename T::X   Type;  
   Type f();   // OK: "Type" is a type-specifer  
   typename T::X g();   // typename required  
   operator typename T::Z();   // typename required      
};  
```  
  
 ve bu,  
  
```  
// C4346c.cpp  
// compile with: /LD /WX  
struct Y {  
   typedef int Y_t;  
};  
  
template<class T>  
struct A {  
   typedef Y A_t;  
};  
  
template<class T>  
struct B {  
   typedef /*typename*/ A<T>::A_t B_t;   // C4346 typename needed here  
   typedef /*typename*/ B_t::Y_t  B_t2;   // typename also needed here  
};  
```