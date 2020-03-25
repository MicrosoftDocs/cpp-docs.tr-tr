---
title: Derleyici hatası C2558
ms.date: 11/04/2016
f1_keywords:
- C2558
helpviewer_keywords:
- C2558
ms.assetid: 822b701e-dcae-423a-b21f-47f36aff9c90
ms.openlocfilehash: 93b6e414f26c56702a1c7ac12863cbcd5063b570
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177501"
---
# <a name="compiler-error-c2558"></a>Derleyici hatası C2558

'tanımlayıcı' : kullanılabilir kopya oluşturucu yok ya da kopya oluşturucu 'açık' olarak belirtildi

Kopya oluşturucusu, bir nesneyi aynı türde başka bir nesneden başlatır. (Nesnenin bir kopyasını oluşturur.) Herhangi bir Oluşturucu tanımlamadıysanız, derleyici varsayılan bir kopya Oluşturucu oluşturur.

### <a name="to-fix-this-error"></a>Bu hatayı düzeltmek için

1. Bu sorun, kopya Oluşturucusu `private`olan bir sınıfı kopyalamak için bir girişim yapıldığında oluşabilir. Çoğu durumda, `private` kopya oluşturucusuna sahip bir sınıf kopyalanmamalıdır. Ortak programlama tekniği, bir sınıfın doğrudan kullanımını engellemek için `private` kopya Oluşturucu bildirir. Sınıf kendisi tarafından kullanılamayabilir ya da düzgün şekilde çalışması için başka bir sınıf gerektirebilir.

   `private` kopya oluşturucusuna sahip bir sınıfın kullanılması güvenli olduğunu belirlerseniz, `private` oluşturucusuna sahip olan sınıftan yeni bir sınıf türetirsiniz ve yeni sınıfta bir `public` veya `protected` kopya Oluşturucusu kullanılabilir hale getirin. Türetilen sınıfı orijinalinin yerine kullanın.

1. Bu sorun, kopya Oluşturucusu açık olan bir sınıfı kopyalamak için bir girişim yapıldığında meydana gelebilir. `explicit` olarak bir kopya Oluşturucu bildirmek, bir sınıfın içindeki/from işlevlerine/döndürmeden nesneleri geçirmeyi/döndürmeyi önler. Açık oluşturucular hakkında daha fazla bilgi için bkz. [Kullanıcı tanımlı tür dönüştürmeleri](../../cpp/user-defined-type-conversions-cpp.md).

1. Bu sorun, `const` başvuru parametresi olmayan bir kopya Oluşturucu kullanılarak `const` olarak belirtilen bir sınıf örneğini kopyalamaya yönelik bir girişim yapıldığında ortaya çıkabilir. Kopya oluşturucuyu const olmayan bir tür başvurusu yerine bir `const` tür başvurusuyla bildirin.
