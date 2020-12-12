---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2601'
title: Derleyici hatası C2601
ms.date: 11/04/2016
f1_keywords:
- C2601
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
ms.openlocfilehash: 373ba519633034ddf63889eb82cd71dccfa4a743
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120002"
---
# <a name="compiler-error-c2601"></a>Derleyici hatası C2601

' function ': yerel işlev tanımları geçersiz

Kod, bir işlev içinde bir işlev tanımlamaya çalışır.

Ya da, C2601 hatası konumundan önce kaynak kodunuzda fazladan bir küme ayracı olabilir.

Aşağıdaki örnek C2601 oluşturur:

```cpp
// C2601.cpp
int main() {
   int i = 0;

   void funcname(int j) {   // C2601
      j++;
   }
}
```
