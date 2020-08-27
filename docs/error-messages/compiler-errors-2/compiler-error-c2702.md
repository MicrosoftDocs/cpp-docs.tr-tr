---
title: Derleyici hatası C2702
description: Microsoft C/C++ derleyicisi hata C2702 açıklar.
ms.date: 08/25/2020
f1_keywords:
- C2702
helpviewer_keywords:
- C2702
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
ms.openlocfilehash: 83210f6ab261a5ae6dd7320182c3f4c3539ff4d1
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898422"
---
# <a name="compiler-error-c2702"></a>Derleyici hatası C2702

> `__except` sonlandırma bloğunda görünmeyebilir

Bir özel durum işleyicisi ( **`__try`** / **`__except`** ) bir blok içinde iç içe olamaz **`__finally`** .

Aşağıdaki örnek C2702 oluşturur:

```cpp
// C2702.cpp
// processor: x86 IPF
int Counter;
int main() {
   __try {}
   __finally {
      __try {}   // C2702
      __except( Counter ) {}   // C2702
   }
}
```
