---
title: Derleyici Hatası C2601 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2601
dev_langs:
- C++
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 522abe9c3cb4b9922a6b307055a3d85f40253793
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062962"
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