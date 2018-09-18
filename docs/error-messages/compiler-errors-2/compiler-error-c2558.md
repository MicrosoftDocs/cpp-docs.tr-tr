---
title: Derleyici Hatası C2558 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2558
dev_langs:
- C++
helpviewer_keywords:
- C2558
ms.assetid: 822b701e-dcae-423a-b21f-47f36aff9c90
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd6f38ff8fbe0c4179addf46a43a35be4237b73e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100844"
---
# <a name="compiler-error-c2558"></a>Derleyici Hatası C2558

'tanımlayıcı' : kullanılabilir kopya oluşturucu yok ya da kopya oluşturucu 'açık' olarak belirtildi

Kopya oluşturucusu, bir nesneyi aynı türde başka bir nesneden başlatır. (Nesnenin bir kopyasını alır.) Derleyici, herhangi bir oluşturucu tanımlamazsanız, varsayılan bir kopya oluşturucu yaratır.

### <a name="to-fix-this-error"></a>Bu hatayı düzeltmek için

1. Kopya Oluşturucusu olan bir sınıfı kopyalama denemesi yapıldığında sorun oluşabilir `private`. Çoğu durumda, bir sınıf olan bir `private` kopya Oluşturucu kopyalanması gerekmez. Yaygın bir programlama tekniği bildiren bir `private` bir sınıfın doğrudan kullanımını önlemek için kopya Oluşturucu. Sınıf kendisi tarafından kullanılamayabilir ya da düzgün şekilde çalışması için başka bir sınıf gerektirebilir.

     Sahip bir sınıfı kullanmanın güvenli olduğunu belirlerseniz bir `private` kopya oluşturucusuna, sahip yeni bir sınıf türetin `private` oluşturucusu ve marka bir `public` veya `protected` Yeni sınıfta kullanılabilir kopya Oluşturucusu. Türetilen sınıfı orijinalinin yerine kullanın.

1. Kopya Oluşturucusu açık olan bir sınıfı kopyalamak için denemesi yapıldığında sorun oluşabilir. Olarak bir kopya Oluşturucu bildirilerek `explicit` geçişini/dönüşünü bir sınıfın işlevlere/işlevlerden engeller. Açık oluşturucular hakkında daha fazla bilgi için bkz: [kullanıcı tanımlı tür dönüşümleri](../../cpp/user-defined-type-conversions-cpp.md).

1. Bildirilen bir sınıf örneği kopyalamak için bir deneme yapıldığında sorun oluşabilir `const` görüntüsünü bir kopya oluşturucu kullanılarak bir `const` parametre başvurusu. İle kopya Oluşturucu bildirin bir `const` başvurusu const olmayan tür başvurusu yerine yazın.