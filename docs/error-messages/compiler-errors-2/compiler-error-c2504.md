---
title: Derleyici hatası C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: 0860f4b860b370f96c2c29046b090d5b205c63ba
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509393"
---
# <a name="compiler-error-c2504"></a>Derleyici hatası C2504

' class ': taban sınıf tanımsız

Temel sınıf tanımlanmış, ancak hiç tanımlanmadı.  Olası nedenler:

1. Eksik içerme dosyası.

1. Dış temel sınıf [extern](../../cpp/extern-cpp.md)ile bildirilmemiş.

Aşağıdaki örnek C2504 oluşturur:

```cpp
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

Tamam

```
class C{};
class D : public C {};
```
