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
ms.openlocfilehash: 750d16bc6fee86d8a3f8b912cdc4c251221dffb2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110878"
---
# <a name="changes-to-conversion-operators"></a>Dönüştürme İşleçlere Değiştirme
Dönüştürme işleçleri sözdizimi C++ için Visual C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 Bir örnektir yazmak için `op_Implicit` dönüştürme belirtmek için. Tanımının işte `MyDouble` dil belirtiminden alınan:  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 Bu, tamsayı, o tamsayıları dönüştüren algoritmanın verilen bildiren bir `MyDouble` tarafından sağlanan `op_Implicit` işleci. Ayrıca, bu dönüştürme örtük olarak derleyici tarafından gerçekleştirilir. Benzer şekilde, verilen bir `MyDouble` nesnesi, iki `op_Explicit` işleçleri bu nesne bir tamsayı ya da yönetilen dönüştürmek için ilgili algoritmaları sağlar `String` varlık. Ancak, kullanıcı tarafından açıkça istenen kadar derleyici dönüştürme gerçekleştirmez.  
  
 C# ' ta şu şekilde görünür:  
  
```  
class MyDouble {  
   public static implicit operator MyDouble( int i );   
   public static explicit operator int( MyDouble val );  
   public static explicit operator string( MyDouble val );   
};  
```  
  
 C++ için Yönetilen Uzantılar daha C# kodu daha C++ gibi görünüyor. Bu yeni söz dizimi durumda değil.  
  
 Bir anahtar sözcük ISO-C++ komitesi sunulan `explicit`, istenmeyen sonuçları - Örneğin, azaltmak için bir `Array` boyut herhangi bir tamsayı örtük dönüştürme gibi tek tamsayı bağımsız değişken sınıfı bir `Array` hangi nesne istemezsiniz olur. Bunu önlemek için bir tasarım deyim bir kukla ikinci bağımsız değişkenin bir oluşturucuya yoludur  
  
 Öte yandan, dönüştürme çifti C++ içinde bir sınıf türü tasarlarken sağlamalıdır değil. En iyi örnek, için standart dize sınıfıdır. Örtük dönüştürme C stili dize alan tek bağımsız değişkenli Oluşturucu değildir. Ancak, bir dize dönüştürme nesne C stili dizeye, ancak bunun yerine bir adlandırılmış işlevi - bu durumda, açıkça çağırmak kullanıcının gerektiren karşılık gelen örtük dönüşüm işleci - sağlamaz `c_str()`.  
  
 Bu nedenle, bir dönüşüm işleci (ve tek bir bildirim biçimine dönüştürme kümesini kapsüllemek) dolaylı/açık davranışı ilişkilendirme sonundasonuçlanandönüşümişleçleriözgünC++desteğinibirgeliştirmegibigörünüyor`explicit` anahtar sözcüğü. Dönüştürme işleçleri Visual C++ dil desteğini örtük bir uygulama dönüştürme algoritmasının destekleme işleci varsayılan davranışı nedeniyle biraz daha az ayrıntılı, C# olduğu aşağıdaki gibi görünür:  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 Başka bir değişiklik olarak bildirilen gibi tek bir bağımsız değişken Oluşturucu kabul edilir olduğunu `explicit`. Bu, çağrısını tetiklemek için açık bir atama gerekmediği anlamına gelir. Ancak, bir açık dönüşüm işleci tanımlanmışsa ve tek bağımsız değişkenli Oluşturucusu çağrılır olduğunu unutmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfta veya Arabirimde Üye Bildirimleri (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)