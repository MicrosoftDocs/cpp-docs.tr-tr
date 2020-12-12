---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2537'
title: Derleyici hatası C2537
ms.date: 11/04/2016
f1_keywords:
- C2537
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
ms.openlocfilehash: 46603ded270b4702d4b7d4de97352547c5f503f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302044"
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
