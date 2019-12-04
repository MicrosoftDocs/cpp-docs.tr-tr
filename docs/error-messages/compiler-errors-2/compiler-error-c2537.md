---
title: Derleyici hatası C2537
ms.date: 11/04/2016
f1_keywords:
- C2537
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
ms.openlocfilehash: 0dfe9f88fcdfda1325150d480670777a4d42d896
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758638"
---
# <a name="compiler-error-c2537"></a>Derleyici hatası C2537

' belirtici ': geçersiz bağlama belirtimi

Olası nedenler:

1. Bağlantı belirticisi desteklenmiyor. Yalnızca "C" bağlantı belirleyicisi desteklenir.

1. "C" bağlantısı, aşırı yüklenmiş işlevler kümesinde birden fazla işlev için belirtildi. Buna izin verilmez.

Aşağıdaki örnek C2537 oluşturur:

```cpp
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```
