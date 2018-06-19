---
title: Sanal işlev mühürleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
- derived classes, virtual functions
- virtual functions, sealing
- __sealed keyword
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c85f4775025d3661fdfbf8967b310fb733f452b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164602"
---
# <a name="sealing-a-virtual-function"></a>Sanal İşlev Mühürleme
Sanal işlev mühürleme sözdizimi için Visual C++ C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 `__sealed` Sonraki türetmeye izin vermeme ya da bir başvuru türü değiştirmek için Yönetilen Uzantılar'anahtar sözcüğü kullanılır (bkz [bir yönetilen sınıf türü bildirimi](../dotnet/declaration-of-a-managed-class-type.md)), veya bir sanal işlev değiştirmeye izin vermeme sonraki yöntemin türetilen bir sınıfta geçersiz kılma. Örneğin:  
  
```  
__gc class base { public: virtual void f(); };  
__gc class derived : public base {  
public:  
   __sealed void f();  
};  
```  
  
 Bu örnekte, `derived::f()` geçersiz kılmaları `base::f()` örnek tabanlı işlev prototipi tam eşleşme. `__sealed` Anahtar sözcüğü gösterir türetilmiş sınıftan devralınan sonraki sınıfın bir geçersiz kılma sağlayamayacağını `derived::f()`.  
  
 Yeni sözdiziminde `sealed` gerçek işlev prototipi önce önceden izin verildiği gibi herhangi bir yerde görünür yerine imza sonra yerleştirilir. Ayrıca, kullanımını `sealed` açık bir kullanımını gerektirir `virtual` da anahtar sözcük. Diğer bir deyişle, doğru çevrilmesi `derived`, yukarıdaki aşağıdaki gibidir:  
  
```  
ref class derived: public base {  
public:  
   virtual void f() override sealed;  
};  
```  
  
 Yokluğu `virtual` anahtar sözcüğü Bu örnekte hatayla sonuçlanır. Bağlamsal anahtar sözcüğü yeni sözdiziminde `abstract` yerine kullanılabilir `=0` saf sanal işlevi belirtmek için. Bu Yönetilen Uzantılar içinde desteklenmiyordu. Örneğin:  
  
```  
__gc class base { public: virtual void f()=0; };  
```  
  
 olarak yazılabilir  
  
```  
ref class base { public: virtual void f() abstract; };  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfta veya arabirimde üye bildirimleri (C + +/ CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)