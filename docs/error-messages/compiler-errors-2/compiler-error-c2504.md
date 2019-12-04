---
title: Derleyici hatası C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: d47d99962d089d873cb9bbdf9baac7eab706fc16
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746896"
---
# <a name="compiler-error-c2504"></a>Derleyici hatası C2504

' class ': taban sınıf tanımsız

Temel sınıf tanımlanmış, ancak hiç tanımlanmadı.  Olası nedenler:

1. Eksik içerme dosyası.

1. Dış temel sınıf [extern](../../cpp/using-extern-to-specify-linkage.md)ile bildirilmemiş.

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
