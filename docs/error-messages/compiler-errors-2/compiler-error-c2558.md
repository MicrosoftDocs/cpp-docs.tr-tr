---
title: Derleyici Hatası C2558
ms.date: 11/04/2016
f1_keywords:
- C2558
helpviewer_keywords:
- C2558
ms.assetid: 822b701e-dcae-423a-b21f-47f36aff9c90
ms.openlocfilehash: b0dca0b19d427cf83238c824739d288a1cfd54d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353020"
---
# <a name="compiler-error-c2558"></a>Derleyici Hatası C2558

'tanımlayıcı' : kullanılabilir kopya oluşturucu yok ya da kopya oluşturucu 'açık' olarak belirtildi

Kopya oluşturucusu, bir nesneyi aynı türde başka bir nesneden başlatır. (Nesnenin bir kopyasını alır.) Derleyici, herhangi bir oluşturucu tanımlamazsanız, varsayılan bir kopya oluşturucu yaratır.

### <a name="to-fix-this-error"></a>Bu hatayı düzeltmek için

1. Kopya Oluşturucusu olan bir sınıfı kopyalama denemesi yapıldığında sorun oluşabilir `private`. Çoğu durumda, bir sınıf olan bir `private` kopya Oluşturucu kopyalanması gerekmez. Yaygın bir programlama tekniği bildiren bir `private` bir sınıfın doğrudan kullanımını önlemek için kopya Oluşturucu. Sınıf kendisi tarafından kullanılamayabilir ya da düzgün şekilde çalışması için başka bir sınıf gerektirebilir.

   Sahip bir sınıfı kullanmanın güvenli olduğunu belirlerseniz bir `private` kopya oluşturucusuna, sahip yeni bir sınıf türetin `private` oluşturucusu ve marka bir `public` veya `protected` Yeni sınıfta kullanılabilir kopya Oluşturucusu. Türetilen sınıfı orijinalinin yerine kullanın.

1. Kopya Oluşturucusu açık olan bir sınıfı kopyalamak için denemesi yapıldığında sorun oluşabilir. Olarak bir kopya Oluşturucu bildirilerek `explicit` geçişini/dönüşünü bir sınıfın işlevlere/işlevlerden engeller. Açık oluşturucular hakkında daha fazla bilgi için bkz: [kullanıcı tanımlı tür dönüşümleri](../../cpp/user-defined-type-conversions-cpp.md).

1. Bildirilen bir sınıf örneği kopyalamak için bir deneme yapıldığında sorun oluşabilir `const` görüntüsünü bir kopya oluşturucu kullanılarak bir `const` parametre başvurusu. İle kopya Oluşturucu bildirin bir `const` başvurusu const olmayan tür başvurusu yerine yazın.