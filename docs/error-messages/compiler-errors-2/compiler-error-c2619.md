---
title: Derleyici hatası C2619
ms.date: 11/04/2016
f1_keywords:
- C2619
helpviewer_keywords:
- C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
ms.openlocfilehash: b64eccac351c6bdd8ac388278a6e264cc7a84868
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220307"
---
# <a name="compiler-error-c2619"></a>Derleyici hatası C2619

' tanımlayıcı ': anonim bir yapıda veya birleşimde statik veri üyesine izin verilmez

Anonim yapının veya birleşimin üyesi bildirilmiştir **`static`** .

Aşağıdaki örnek C2619 oluşturur ve statik anahtar sözcüğü kaldırarak nasıl düzeltileceğini gösterir.

```cpp
// C2619.cpp
int main() {
   union { static int j; };  // C2619
   union { int j; };  // OK
}
```
