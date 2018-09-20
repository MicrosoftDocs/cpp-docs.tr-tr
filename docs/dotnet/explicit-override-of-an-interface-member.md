---
title: Arabirim üyesini açık geçersiz kılma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, explicit overrides
- overriding functions
- interface members, explicit overrides
- functions [C++], overriding
- explicit override of virtual function
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 57c26c1185eff0e88e18ef23cb8506fb1fed407a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409031"
---
# <a name="explicit-override-of-an-interface-member"></a>Arabirim Üyesini Açık Geçersiz Kılma

Söz dizimi bir sınıf içinde arabirim üyesini açık geçersiz kılma bildirmek için C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

Genellikle, iki örneği - bir sınıfı nesnelerini bir arabirim tanıtıcısı üzerinden yönlendirildiği zaman kullanılır ve sınıf nesnelerine kullanıldığında sınıf arabirimi üzerinden kullanılan bir arabirimi uygulayan bir sınıf içinde arabirim üyesini sunmak istiyorsunuz. Örneğin:

```
public __gc class R : public ICloneable {
   // to be used through ICloneable
   Object* ICloneable::Clone();

   // to be used through an R
   R* Clone();
};
```

Yönetilen Uzantılar'arabirim yönteminin açık bir bildirimi arabirimin adını tam yöntemin adı sağlayarak bunu. Nitelenmemiş sınıfa özgü örneğidir. Bu durum dönüş değerini gereken ihtiyacını ortadan kaldırır `Clone`, bu örnekte, açık bir örneği üzerinden çağrıldığında `R`.

Yeni sözdiziminde, yerini alan yönetilen uzantıları söz dizimi genel bir geçersiz kılma mekanizması sunulmuştur. Bizim örneğimizde gibi yazılması:

```
public ref class R : public ICloneable {
public:
   // to be used through ICloneable
   virtual Object^ InterfaceClone() = ICloneable::Clone;

   // to be used through an R
   virtual R^ Clone();
};
```

Bu düzeltme açıkça geçersiz kılınmasını arabirim üyesi olmasını gerektirir sınıf içinde benzersiz bir adı verilir. Burada, garip adını sağladığınız `InterfaceClone`. Davranış hala - aracılığıyla yapılan bir çağrı aynıdır `ICloneable` arabirimi çağırır, yeniden adlandırılmış `InterfaceClone`, while türünde bir nesne çağrısıyla `R` ikinci çağırır `Clone` örneği.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfta veya Arabirimde Üye Bildirimleri (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[Açık Geçersiz Kılmalar](../windows/explicit-overrides-cpp-component-extensions.md)