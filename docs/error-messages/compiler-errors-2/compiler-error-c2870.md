---
title: Derleyici Hatası C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: f61281da23e46236e7fce496a4d89086e5d6c0ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546385"
---
# <a name="compiler-error-c2870"></a>Derleyici Hatası C2870

'name': bir ad alanı tanımı dosya kapsamında veya hemen başka bir ad alanı tanımı içinde yer almalıdır

Ad alanı tanımlı `name` yanlış. Ad alanları tanımlanan, dosya kapsamında (dışındaki tüm bloklar ve sınıflar) veya başka bir ad alanı içinde hemen.

Aşağıdaki örnek, C2870 oluşturur:

```
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```