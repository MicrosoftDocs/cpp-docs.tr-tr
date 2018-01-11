---
title: "Sanal işlev mühürleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sealed keyword [C++]
- derived classes, virtual functions
- virtual functions, sealing
- __sealed keyword
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 48d52a2697289197555438847ba2fcb86aeb3235
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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