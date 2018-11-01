---
title: Derleyici Hatası C2345
ms.date: 11/04/2016
f1_keywords:
- C2345
helpviewer_keywords:
- C2345
ms.assetid: e1cc88b0-0223-4d07-975b-fa99956a82bd
ms.openlocfilehash: ceb2a835ca94399f27640628105afcde986af1b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479111"
---
# <a name="compiler-error-c2345"></a>Derleyici Hatası C2345

align(Value): Geçersiz hizalama değeri

Bir değere geçirilen [hizalama](../../cpp/align-cpp.md) izin verilen aralığın dışında bir anahtar sözcüğü.

Aşağıdaki kod, C2345 oluşturur.

```
// C2345.cpp
// compile with: /c
__declspec(align(0)) int a;   // C2345
__declspec(align(1)) int a;   // OK
```