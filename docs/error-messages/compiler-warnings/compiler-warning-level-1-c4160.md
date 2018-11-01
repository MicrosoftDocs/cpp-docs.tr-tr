---
title: Derleyici Uyarısı (düzey 1) C4160
ms.date: 08/27/2018
f1_keywords:
- C4160
helpviewer_keywords:
- C4160
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
ms.openlocfilehash: 988c1fcbe0826582dceaa527811c688711fd8906
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428051"
---
# <a name="compiler-warning-level-1-c4160"></a>Derleyici Uyarısı (düzey 1) C4160

> #<a name="pragma-pop--did-not-find-previously-pushed-identifier-identifier"></a>pragma (pop,...): daha önce bulamadı '*tanımlayıcı*'

## <a name="remarks"></a>Açıklamalar

Kaynak kodunda bir pragma deyimi değil itilmiş bir tanımlayıcı pop dener. Bu uyarıyı engellemek için POP tanımlayıcı düzgün itilmiş emin olun.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4160 oluşturur ve bu sorunun nasıl gösterir:

```cpp
// C4160.cpp
// compile with: /W1
#pragma pack(push)

#pragma pack(pop, id)   // C4160
// use identifier when pushing to resolve the warning
// #pragma pack(push, id)

int main() {
}
```