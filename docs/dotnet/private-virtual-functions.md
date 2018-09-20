---
title: Özel sanal işlevler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, private
- derived classes, virtual functions
- access modifiers [C++], for class members
- member access [C++], virtual members
ms.assetid: 04448086-bf72-44be-9c1f-dfda1744949e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0058d023268fa4d9ca5abe802ff45856e9855dc7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418079"
---
# <a name="private-virtual-functions"></a>Özel Sanal İşlevler

Özel sanal işlevler, türetilmiş sınıflarda işlenme şekli, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

Yönetilen Uzantılar'da, bir sanal işlev erişim düzeyini türetilmiş bir sınıf içinde geçersiz kılınması yeteneğini kısıtlamaz. Yeni sözdiziminde, bir sanal işlev erişim bir temel sınıf sanal işlevi geçersiz kılamaz. Örneğin:

```
__gc class MyBaseClass {
   // inaccessible to a derived class
   virtual void g();
};

__gc class MyDerivedClass : public MyBaseClass {
public:
   // okay in Managed Extensions; g() overrides MyBaseClass::g()
   // error in new syntax; cannot override: MyBaseClass::g() is inaccessible
   void g();
};
```

Bu tür bir tasarım yeni sözdizimi üzerine gerçek eşlemesi yok. Bir yalnızca temel sınıf üyelerinin erişilebilir - diğer bir deyişle, özel olmayan yapmak zorunda kalır. Devralınan yöntemleri aynı erişimi taşımaları gerekmez. Bu örnekte, az bozucu değişiklik MyBaseClass üyeyi olmaktır `protected`. Bu şekilde yöntemi MyBaseClass aracılığıyla genel programın erişmeye hala kullanılamaz.

```
ref class MyBaseClass {
protected:
   virtual void g();
};

ref class MyDerivedClass : MyBaseClass {
public:
   virtual void g() override;
};
```

Unutmayın açık olmaması `virtual` temel sınıfta, yeni bir sözdizimi anahtar sözcüğü, bir uyarı iletisi oluşturur.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfta veya Arabirimde Üye Bildirimleri (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)
