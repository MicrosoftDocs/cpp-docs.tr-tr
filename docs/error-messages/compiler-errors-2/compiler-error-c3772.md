---
title: "Derleyici Hatası C3772 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3772
dev_langs: C++
helpviewer_keywords: C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3290a3be06ecc223bfc87e39ed068d187d4f95c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3772"></a>Derleyici Hatası C3772
"name": Geçersiz arkadaş şablon bildirimi  
  
Sınıf şablonu uzmanlık arkadaş bildirmek için geçersiz. Sınıf şablonu açık ya da kısmi bir uzmanlaşması bildirme ve o uzmanlık arkadaş aynı deyiminde bildirin. *Adı* yer tutucu geçersiz bildirimi tanımlar.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Sınıf şablonu uzmanlık arkadaş bildirme.  
  
-   Uygunsa, uygulamanız için sınıf şablonunun arkadaş bildirme veya belirli bir açık veya kısmi uzmanlığı arkadaş bildirin.  
  
## <a name="example"></a>Örnek  
 Sınıf şablonu kısmi uzmanlığı arkadaş bildirdiğinden aşağıdaki kod örneğinde başarısız olur.  
  
```cpp  
// c3772.cpp  
// compile with: /c  
  
// A class template.  
    template<class T> class A {};  
  
// A partial specialization of the class template.  
    template<class T> class A<T*> {};  
  
// An explicit specialization.  
    template<> class A<char>;  
  
class X {  
// Invalid declaration of a friend of a partial specialization.  
    template<class T> friend class A<T*>; // C3772  
  
// Instead, if it is appropriate for your application, declare a   
// friend of the class template. Consequently, all specializations   
// of the class template are friends:  
//    template<class T> friend class A;  
// Or declare a friend of a particular partial specialization:  
//    friend class A<int*>;  
// Or declare a friend of a particular explicit specialization:  
//    friend class A<char>;  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Şablonları](../../cpp/templates-cpp.md)   
[Şablonu özelleştirme](../../cpp/template-specialization-cpp.md)   
