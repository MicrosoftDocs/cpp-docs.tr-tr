---
title: Derleyici Hatası C3772 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3772
dev_langs:
- C++
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01003a4d474b80c152d271546f659d418f3c4df7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275456"
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
[Şablon Uzmanlığı](../../cpp/template-specialization-cpp.md)   
