---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2109'
title: Derleyici hatası C2109
ms.date: 11/04/2016
f1_keywords:
- C2109
helpviewer_keywords:
- C2109
ms.assetid: 2d1ac79d-a985-4904-a38b-b270578d664d
ms.openlocfilehash: b47a0034aade2c3afda3e6785fa2dcd3215b3356
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341288"
---
# <a name="compiler-error-c2109"></a>Derleyici hatası C2109

indis için dizi veya işaretçi türü gerekir

Alt simge, dizi olmayan bir değişkende kullanıldı.

Aşağıdaki örnek C2109 oluşturur:

```cpp
// C2109.cpp
int main() {
   int a, b[10] = {0};
   a[0] = 1;   // C2109
   b[0] = 1;   // OK
}
```
