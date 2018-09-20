---
title: Dönüştürme işleçleri değişiklikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- conversion operators
- operators [C++], explicit type conversion
- type conversion, explicit conversions
- conversions, explicit
- explicit keyword [C++]
ms.assetid: 9b83925c-71b7-4bd3-ac2e-843dd7c7f184
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 03b17c5abc559289a9f85a10b9c5914b49498922
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381120"
---
# <a name="changes-to-conversion-operators"></a>Dönüştürme İşleçlere Değiştirme

Dönüştürme işleçleri için sözdizimi, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

Bir örnektir yazılacak `op_Implicit` dönüştürme belirtmek için. Bir tanımı işte `MyDouble` dil belirtiminden alınan:

```
__gc struct MyDouble {
   static MyDouble* op_Implicit( int i );
   static int op_Explicit( MyDouble* val );
   static String* op_Explicit( MyDouble* val );
};
```

Bu, bir tamsayı, algoritma bu değeri tamsayıya dönüştürmek için verilen bildiren bir `MyDouble` tarafından sağlanan `op_Implicit` işleci. Ayrıca, bu dönüştürme örtük olarak derleyici tarafından gerçekleştirilir. Benzer şekilde, verilen bir `MyDouble` nesnesi, iki `op_Explicit` işleçleri, bu nesne bir tamsayı ya da yönetilen dönüştürmek için ilgili algoritmaları sağlamak `String` varlık. Ancak, kullanıcı tarafından açıkça istenmedikçe derleyici dönüştürme gerçekleştirmez.

C# içinde bunu şu şekilde görünür:

```
class MyDouble {
   public static implicit operator MyDouble( int i );
   public static explicit operator int( MyDouble val );
   public static explicit operator string( MyDouble val );
};
```

C++ için Yönetilen Uzantılar daha C# kod daha C++ gibi görünür. Bu yeni söz dizimini durumda değil.

Bir anahtar sözcüğü, ISO-C++ komitesi sunulan `explicit`, istenmeyen sonuçları - Örneğin, azaltmak için bir `Array` boyut örtük olarak herhangi bir tamsayı olarak tek bir tam sayı bağımsız değişkenini alan sınıfının bir `Array` hangi nesne siz bunu istemezsiniz olur. Bunu önlemek için bir işlevsiz bir ikinci bağımsız değişkeni bir oluşturucu için bir tasarım deyimidir yoludur

Öte yandan, dönüştürme çifti C++ içinde bir sınıf türü tasarlarken sağlamalıdır değil. Söz konusu en iyi örnek standart dize sınıfıdır. Örtük dönüştürme, C stili dize alma tek bağımsız değişkenli oluşturucudur. Ancak, bir dize dönüştürme nesnesi C stili dizeye, ancak bunun yerine bir adlandırılmış işlev - bu durumda, açıkça çağırmak kullanıcı gerektirir karşılık gelen örtük dönüştürme işleci - sağlamaz `c_str()`.

Bu nedenle, bir örtük/açık bir dönüştürme operatörünün (ve tek bir bildirim biçimine dönüştürme kümesini kapsüllemek) davranışı ilişkilendirme özgün C++ desteği için sonundasonuçlanandönüştürmeişleçleriiçinbirgeliştirmegibigörünüyor`explicit` anahtar sözcüğü. Dönüştürme işleçleri için Visual C++ dil desteği, örtük bir dönüştürme algoritması uygulamaya destekleyici işlecinin varsayılan davranışı nedeniyle biraz daha az ayrıntılı, C# olduğu aşağıdaki gibi görünür:

```
ref struct MyDouble {
public:
   static operator MyDouble^ ( int i );
   static explicit operator int ( MyDouble^ val );
   static explicit operator String^ ( MyDouble^ val );
};
```

Tek bir bağımsız değişken Oluşturucu olarak bildirilen yokmuş gibi kabul edilir başka bir değişikliktir `explicit`. Bu, çağrısını tetiklemek için açık bir tür dönüştürme gerekli olduğu anlamına gelir. Ancak, açık bir dönüştürme operatörü tanımlı ise ve tek bağımsız değişkenli Oluşturucu çağrılır olduğunu unutmayın.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfta veya Arabirimde Üye Bildirimleri (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)