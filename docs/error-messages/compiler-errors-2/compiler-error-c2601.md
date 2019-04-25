---
title: Derleyici Hatası C2601
ms.date: 11/04/2016
f1_keywords:
- C2601
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
ms.openlocfilehash: f18819e5f078cb85121160af1d4a3fc24a365a68
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62215591"
---
# <a name="compiler-error-c2601"></a>Derleyici Hatası C2601

'function': yerel işlev tanımları geçersiz

Kod, bir işlevin içindeki bir fonksiyon tanımlayın dener.

Veya, kaynak kodunuzdaki C2601 hatanın konumunu önce ek bir küme ayracı olabilir.

Aşağıdaki örnek, C2601 oluşturur:

```
// C2601.cpp
int main() {
   int i = 0;

   void funcname(int j) {   // C2601
      j++;
   }
}
```