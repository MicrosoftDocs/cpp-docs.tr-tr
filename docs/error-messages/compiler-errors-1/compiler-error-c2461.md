---
title: Derleyici hatası C2461
ms.date: 11/04/2016
f1_keywords:
- C2461
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
ms.openlocfilehash: 3d290bd2288f76d0ddefa2057e3e01c9edc3cbc7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205328"
---
# <a name="compiler-error-c2461"></a>Derleyici hatası C2461

> '*Class*': Oluşturucu sözdiziminde biçimsel parametreler eksik

Sınıf için Oluşturucu herhangi bir biçimsel parametre belirtmiyor. Bir oluşturucunun bildirimi, biçimsel bir parametre listesi belirtmelidir. Liste boş olabilir.

Bu sorunu onarmak için, *sınıf*::**sınıfının*bildiriminden sonra bir çift ayraç ekleyin.

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
