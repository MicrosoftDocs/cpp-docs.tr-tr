---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2101'
title: Derleyici hatası C2101
ms.date: 11/04/2016
f1_keywords:
- C2101
helpviewer_keywords:
- C2101
ms.assetid: 42f0136f-8cc1-4f2b-be1c-721ec9278e66
ms.openlocfilehash: b41aa520d0aba3970689bf0bb5d65db5effb36aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278577"
---
# <a name="compiler-error-c2101"></a>Derleyici hatası C2101

Sabitte ' & '

Address-of işlecinin ( `&` ) işlenen olarak bir l değeri olmalıdır.

Aşağıdaki örnek C2101 oluşturur:

```cpp
// C2101.cpp
int main() {
   char test;
   test = &'a';   // C2101
   test = 'a';   // OK
}
```
