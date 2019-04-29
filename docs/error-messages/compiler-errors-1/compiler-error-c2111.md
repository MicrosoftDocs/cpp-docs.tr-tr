---
title: Derleyici Hatası C2111
ms.date: 11/04/2016
f1_keywords:
- C2111
helpviewer_keywords:
- C2111
ms.assetid: 38fd42ec-1480-4a44-aaca-ae4593ed5f50
ms.openlocfilehash: 9545e44518a7a377378929d684bf08573a214b18
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364421"
---
# <a name="compiler-error-c2111"></a>Derleyici Hatası C2111

'+': işaretçi toplama için tam sayı işlenen gerekir

Artı kullanarak bir işaretçiye nonintegral değer eklemek için bir girişimde bulunuldu ( `+` ) işleci.

Aşağıdaki örnek, C2111 oluşturur:

```
// C2111.cpp
int main() {
   int *a = 0, *pa = 0, b = 0;
   double d = 0.00;

   a = pa + d;   // C2111
   a = pa + b;   // OK
}
```