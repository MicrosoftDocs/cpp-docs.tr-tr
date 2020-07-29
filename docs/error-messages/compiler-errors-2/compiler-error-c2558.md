---
title: Derleyici hatası C2558
ms.date: 11/04/2016
f1_keywords:
- C2558
helpviewer_keywords:
- C2558
ms.assetid: 822b701e-dcae-423a-b21f-47f36aff9c90
ms.openlocfilehash: 2504b42f49ccb040f676f0aead8f243d33c7dd1a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207751"
---
# <a name="compiler-error-c2558"></a>Derleyici hatası C2558

'tanımlayıcı' : kullanılabilir kopya oluşturucu yok ya da kopya oluşturucu 'açık' olarak belirtildi

Kopya oluşturucusu, bir nesneyi aynı türde başka bir nesneden başlatır. (Nesnenin bir kopyasını oluşturur.) Herhangi bir Oluşturucu tanımlamadıysanız, derleyici varsayılan bir kopya Oluşturucu oluşturur.

### <a name="to-fix-this-error"></a>Bu hatayı düzeltmek için

1. Bu sorun, kopya Oluşturucusu olan bir sınıfı kopyalamak için bir girişim yapıldığında meydana gelebilir **`private`** . Çoğu durumda, kopya Oluşturucusu olan bir sınıf **`private`** kopyalanmamalıdır. Ortak programlama tekniği **`private`** , bir sınıfın doğrudan kullanımını engellemek için bir kopya Oluşturucu bildirir. Sınıf kendisi tarafından kullanılamayabilir ya da düzgün şekilde çalışması için başka bir sınıf gerektirebilir.

   Bir kopya oluşturucusuna sahip bir sınıfın kullanılması güvenli olduğunu belirlerseniz **`private`** , oluşturucuya sahip olan sınıftan yeni bir sınıf türetirsiniz **`private`** ve **`public`** **`protected`** Yeni sınıfta bir veya kopya Oluşturucusu kullanılabilir hale getirin. Türetilen sınıfı orijinalinin yerine kullanın.

1. Bu sorun, kopya Oluşturucusu açık olan bir sınıfı kopyalamak için bir girişim yapıldığında meydana gelebilir. Bir kopya Oluşturucu bildirimi **`explicit`** , bir sınıfın nesnelerinin/from işlevlerine geçirilmesi/döndürülmelerini engeller. Açık oluşturucular hakkında daha fazla bilgi için bkz. [Kullanıcı tanımlı tür dönüştürmeleri](../../cpp/user-defined-type-conversions-cpp.md).

1. Bu sorun, **`const`** başvuru parametresi olmayan bir kopya Oluşturucu kullanılarak belirtilen bir sınıf örneğini kopyalamaya yönelik bir girişim yapıldığında ortaya çıkabilir **`const`** . Kopya oluşturucuyu **`const`** const olmayan bir tür başvurusu yerine tür başvurusuyla bildirin.
