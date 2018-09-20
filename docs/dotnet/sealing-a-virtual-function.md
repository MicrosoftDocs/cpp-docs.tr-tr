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
ms.openlocfilehash: 69ac614d55ade10b94621da2a3eb1c43d25ebaf5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385189"
---
# <a name="sealing-a-virtual-function"></a>Sanal İşlev Mühürleme

Sanal işlev mühürleme sözdizimi, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

`__sealed` Sonraki türetmeye izin vermeme ya da bir başvuru türü değiştirmek için Yönetilen Uzantılar'anahtar sözcüğü kullanılır (bkz [bir yönetilen sınıf türü bildirimi](../dotnet/declaration-of-a-managed-class-type.md)), veya bir sanal işlev değiştirmeye izin vermeme sonraki yöntemin türetilen bir sınıfta geçersiz kılma. Örneğin:

```
__gc class base { public: virtual void f(); };
__gc class derived : public base {
public:
   __sealed void f();
};
```

Bu örnekte, `derived::f()` geçersiz kılmalar `base::f()` örnek tabanlı tam eşleşme işlev prototipi. `__sealed` Anahtar sözcüğü gösterir türetilmiş sınıftan devralınan bir sonraki sınıfı geçersiz kılma sağlayamayacağını `derived::f()`.

Yeni sözdiziminde `sealed` önceden izin verildiği gibi gerçek işlev prototipinden önce herhangi bir yerine imza sonra yerleştirilir. Ayrıca, kullanımını `sealed` açık kullanımını gerektirir `virtual` de anahtar sözcüğü. Diğer bir deyişle, doğru çevirisi `derived`, yukarıdaki aşağıdaki gibidir:

```
ref class derived: public base {
public:
   virtual void f() override sealed;
};
```

Olmaması `virtual` Bu örnekte anahtar sözcüğü hatayla sonuçlanır. Yeni sözdiziminde, bağlamsal anahtar sözcüğü `abstract` yerine kullanılan `=0` saf sanal işlevi belirtmek için. Bu, Yönetilen Uzantılar'içinde desteklenmiyordu. Örneğin:

```
__gc class base { public: virtual void f()=0; };
```

şeklinde yeniden yazılabilir

```
ref class base { public: virtual void f() abstract; };
```

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfta veya Arabirimde Üye Bildirimleri (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[sealed](../windows/sealed-cpp-component-extensions.md)