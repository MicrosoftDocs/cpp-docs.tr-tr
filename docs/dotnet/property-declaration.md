---
title: Özellik bildiriminde | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __property keyword
- declaring properties, C++
- property keyword [C++]
ms.assetid: de169378-a8b8-49f4-a586-76bffc9b5c9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 019b8eae17952bfe53fd8fbf14db4bafce1bf463
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438307"
---
# <a name="property-declaration"></a>Özellik Bildirimi

Yönetilen bir sınıftaki bir özelliği bildirme şekilde, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

Yönetilen uzantılarındaki tasarım, her `set` veya `get` özellik erişimcisi, bağımsız bir yöntem olarak belirtilir. Her yöntem bildiriminin ön ekine sahip `__property` anahtar sözcüğü. Yöntem adı ile başlayan `set_` veya `get_` özelliği (olarak kullanıcıya görünür) gerçek adını ardında. Bu nedenle, bir `Vector` sağlayan bir `x` koordine `get` özellik, adı `get_x` ve kullanıcı olarak çağıracaktır `x`. Bu adlandırma kuralı ve yöntemlerin ayrı belirtimi, temel alınan çalışma zamanı uygulaması özelliğin gerçekten yansıtır. Örneğin, İşte bizim `Vector` koordinat özellikler kümesi ile:

```
public __gc __sealed class Vector {
public:
   __property double get_x(){ return _x; }
   __property double get_y(){ return _y; }
   __property double get_z(){ return _z; }

   __property void set_x( double newx ){ _x = newx; }
   __property void set_y( double newy ){ _y = newy; }
   __property void set_z( double newz ){ _z = newz; }
};
```

Bu özellik ile ilişkilendirilmiş işlevlerini dışarı yayar ve sözcüksel olarak alır ve ilişkili kümeleri birleştirmek kullanıcının gerektirir. Ayrıca, ayrıntılıdır. Dahası, C# gibi yeni sözdiziminde `property` anahtar sözcüğü, özelliğin ve eksiz adını türüne göre izlendiği. `set` Ve `get` erişim yöntemleri, aşağıdaki özellik adını bir blok içinde yerleştirilir. C#, erişim metodun imzası belirtilir. Örneğin, yeni sözdizimine çevrilmiş kodu Yukarıdaki örnek aşağıdadır.

```
public ref class Vector sealed {
public:
   property double x {
      double get() {
         return _x;
      }

      void set( double newx ) {
         _x = newx;
      }
   } // Note: no semi-colon
};
```

Özellik erişim yöntemleri farklı erişim düzeyleri - gibi yansıtmak durumunda bir `public get` ve `private` veya `protected set`, bir açık erişim etiketi belirtilebilir. Varsayılan olarak, erişim düzeyi özelliği, kapsayan erişim düzeyi yansıtır. Örneğin, yukarıdaki tanımı içinde `Vector`hem `get` ve `set` yöntemler `public`. Yapmak `set` yöntemi `protected` veya `private`, tanımı aşağıdaki gibi değiştirilmesi gerekir:

```
public ref class Vector sealed {
public:
   property double x {
      double get() {
         return _x;
      }

   private:
      void set( double newx ) {
         _x = newx;
      }

   } // note: extent of private culminates here

// note: dot is a public method of Vector
double dot( const Vector^ wv );

// etc.
};
```

Özellik kapanış ayracı veya ek erişim anahtar belirtimi kadar bir erişim anahtar sözcüğü bir özellik içinde kapsamını genişletir. Özellik tanımlandığı kapsayan erişim düzeyi özelliği tanımı dışında genişletilmez. Yukarıdaki bildirimde, örneğin, `Vector::dot()` ortak bir yöntemdir.

Üç set/get özelliklerini yazma `Vector` koordinatları üç adımdan oluşur:

1. uygun türde bir özel durum üyesi bildirin.

1. değerini almak istediğinde, bunu döndürür.

1. Yeni bir değer atayabilirsiniz.

Yeni sözdiziminde, bir toplu özellik sözdizimi, bu kullanım şekillerini otomatikleştiren kullanılabilir:

```
public ref class Vector sealed {
public:
   // equivalent shorthand property syntax
   property double x;
   property double y;
   property double z;
};
```

İlgi çekici özellik toplu değer sözdizimi yan etkisi, backstage durum üyesi derleyici tarafından oluşturulmasına rağmen sınıf dışında set/get erişimcileri aracılığıyla erişilebilir olmadığını ' dir.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfta veya Arabirimde Üye Bildirimleri (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[property](../windows/property-cpp-component-extensions.md)