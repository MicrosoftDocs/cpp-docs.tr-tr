---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2461'
title: Derleyici hatası C2461
ms.date: 11/04/2016
f1_keywords:
- C2461
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
ms.openlocfilehash: 788c8e475bd38b829ca8426137569a5d8a083f18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341834"
---
# <a name="compiler-error-c2461"></a>Derleyici hatası C2461

> '*Class*': Oluşturucu sözdiziminde biçimsel parametreler eksik

Sınıf için Oluşturucu herhangi bir biçimsel parametre belirtmiyor. Bir oluşturucunun bildirimi, biçimsel bir parametre listesi belirtmelidir. Liste boş olabilir.

Bu sorunu onarmak için, *sınıf*::**sınıfının* bildiriminden sonra bir çift ayraç ekleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2461 nasıl düzeltileceğini göstermektedir:

```cpp
// C2461.cpp
// compile with: /c
class C {
   C::C;     // C2461
   C::C();   // OK
};
```
