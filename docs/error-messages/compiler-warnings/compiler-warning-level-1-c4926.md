---
title: Derleyici Uyarısı (düzey 1) C4926 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4926
dev_langs:
- C++
helpviewer_keywords:
- C4926
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1942c334f06dce7a8f208f01cae6e2da1b6bb6cf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087948"
---
# <a name="compiler-warning-level-1-c4926"></a>Derleyici Uyarısı (düzey 1) C4926

'identifier': simge zaten tanımlandı: öznitelikler yoksayıldı

İleri dönük bildirimi bulundu, ancak aynı ada sahip bir öznitelik atanmış yapı zaten mevcut. Öznitelikleri İleri dönük bildirimi için yoksayılır.

Aşağıdaki örnek, C4926 oluşturur:

```
// C4926.cpp
// compile with: /W1
[module(name="MyLib")];

[coclass]
struct a {
};

[coclass]
struct a;   // C4926

int main() {
}
```