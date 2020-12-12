---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2619'
title: Derleyici hatası C2619
ms.date: 11/04/2016
f1_keywords:
- C2619
helpviewer_keywords:
- C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
ms.openlocfilehash: 2ca9a8379901703299e89e71671ec0270c1ff1e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123558"
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
