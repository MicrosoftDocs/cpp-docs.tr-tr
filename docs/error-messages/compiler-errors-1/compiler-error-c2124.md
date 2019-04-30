---
title: Derleyici Hatası C2124
ms.date: 11/04/2016
f1_keywords:
- C2124
helpviewer_keywords:
- C2124
ms.assetid: 93392aaa-5582-4d68-8cc5-bd9c62a0ae7e
ms.openlocfilehash: 82bc4447aaf27190c013edf48a20a56c57a646c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397659"
---
# <a name="compiler-error-c2124"></a>Derleyici Hatası C2124

bölme veya mod alma sıfıra

Bir sabit ifade bir sıfır paydası sahiptir. Hatayı gidermek için sıfır bölmeyin.

Aşağıdaki örnek, C2124 oluşturur:

```
// C2124.cpp
int main() {
  int i = 1 / 0;   // C2124  do not divide by zero
  int i2 = 12 / 2;   // OK
}
```