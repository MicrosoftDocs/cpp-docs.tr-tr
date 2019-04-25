---
title: Derleyici Hatası C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: f61281da23e46236e7fce496a4d89086e5d6c0ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165053"
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