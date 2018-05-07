---
title: Derleyici Hatası C3771 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3771
dev_langs:
- C++
helpviewer_keywords:
- C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8adfdb1562cc9efbe208bd7c887b7c4aa77ddd82
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3771"></a>Derleyici Hatası C3771
"tanımlayıcı": arkadaş bildirimi yakın ad alanı kapsamda bulunamadı  
  
Belirtilen şablonu sınıfı şablonu bildirimi *tanımlayıcısı* geçerli ad içinde bulunamıyor.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Sınıf şablonu bildirimi şablon tanımlayıcısı için geçerli ad alanında tanımlı değil veya şablon tanımlayıcı bir tam ad olduğundan emin olun.  
  
## <a name="example"></a>Örnek  
Aşağıdaki kod örneği sınıf şablonunu ve ad alanı işlevinde bildirir `NA`, ancak bir ad alanı arkadaş işlevi şablonunda bildirmeye `NB`.  
  
```cpp  
// C3771.cpp   
// compile with: /c  
  
namespace NA {  
template<class T> class A {  
    void aFunction(T t) {};  
    };  
}  
// using namespace NA;  
namespace NB {  
    class X {  
        template<class T> friend void A<T>::aFunction(T); // C3771  
// try the following line instead  
//      template<class T> friend void NA::A<T>::aFunction(T);  
// or try "using namespace NA;" instead.  
    };  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Şablonlar](../../cpp/templates-cpp.md)  