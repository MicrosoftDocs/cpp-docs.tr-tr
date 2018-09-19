---
title: Derleyici Uyarısı (düzey 1 ve 4) C4112 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9015a7ee7a0b71d3c6aafd3e3b32d4ea1b07f108
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110555"
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Derleyici Uyarısı (düzey 1 ve 4) C4112

\#Satır numarası ile 1 arasındaki bir tamsayı gerektirir

[#Line](../../preprocessor/hash-line-directive-c-cpp.md) yönergesi belirtir izin verilen aralık dışında bir tam sayı parametresi.

Belirtilen parametre 1'den az ise 1 satır sayacı sıfırlanır. Belirtilen parametre sayısından büyükse *numarası*, derleyici tarafından tanımlanan sınırının, satır sayaç değiştirilmez. Bu düzey 1 uyarısı ANSI Uyumluluğu altında olduğu ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ve düzey 4 uyarısı Microsoft uzantılı ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

Aşağıdaki örnek, C4112 oluşturur:

```
// C4112.cpp
// compile with: /W4
#line 0   // C4112, value must be between 1 and number

int main() {
}
```