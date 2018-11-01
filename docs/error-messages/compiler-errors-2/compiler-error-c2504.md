---
title: Derleyici Hatası C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: 8f428699aa14cbd1f021a57ed8dcabefa8b24c16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444397"
---
# <a name="compiler-error-c2504"></a>Derleyici Hatası C2504

'class': taban sınıf tanımsız

Temel sınıf bildirildi, ancak hiçbir zaman tanımlı.  Olası nedenler:

1. İçerme dosyası eksik.

1. Dış temel sınıf bildirilmemiş olan [extern](../../cpp/using-extern-to-specify-linkage.md).

Aşağıdaki örnek, C2504 oluşturur:

```
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

TAMAM

```
class C{};
class D : public C {};
```