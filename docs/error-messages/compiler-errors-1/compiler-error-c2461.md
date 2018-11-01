---
title: Derleyici Hatası C2461
ms.date: 11/04/2016
f1_keywords:
- C2461
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
ms.openlocfilehash: e8f82ed4ce8ad77a22961a42c8e9a256e6f647db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535141"
---
# <a name="compiler-error-c2461"></a>Derleyici Hatası C2461

> '*sınıfı*': Oluşturucu sözdiziminde biçimsel parametreler eksik

Sınıf için oluşturucu herhangi bir biçimsel parametre belirtmiyor. Bir oluşturucu bildirimi bir biçimsel parametre listesi belirtmelisiniz. Liste boş olabilir.

Bu sorunu gidermek için bildirimi sonra parantez çifti Ekle *sınıfı*:: **sınıfı*.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2461 düzeltme işlemi gösterilmektedir:

```cpp
// C2461.cpp
// compile with: /c
class C {
   C::C;     // C2461
   C::C();   // OK
};
```