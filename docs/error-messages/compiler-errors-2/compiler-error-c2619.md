---
title: Derleyici Hatası C2619
ms.date: 11/04/2016
f1_keywords:
- C2619
helpviewer_keywords:
- C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
ms.openlocfilehash: f82b315a3e7ae4bb1f6d281e1d80ddc2c7fb0dea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662924"
---
# <a name="compiler-error-c2619"></a>Derleyici Hatası C2619

'identifier': bir anonim bir yapı veya birleşim statik veri üyesine izin verilmez

Bir anonim bir yapı veya birleşim üyesi bildirildiği `static`.

Aşağıdaki örnek, C2619 oluşturur ve static anahtar sözcüğü kaldırarak bu sorunun nasıl gösterir.

```
// C2619.cpp
int main() {
   union { static int j; };  // C2619
   union { int j; };  // OK
}
```