---
title: Derleyici Uyarısı (düzey 4) C4932
ms.date: 11/04/2016
f1_keywords:
- C4932
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
ms.openlocfilehash: 992e047f31e4a30edd29ba6110bf119d2bc8928b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230603"
---
# <a name="compiler-warning-level-4-c4932"></a>Derleyici Uyarısı (düzey 4) C4932

__identifier (tanımlayıcı) ve \_ _identifier (tanımlayıcı) ayırt edilemez

Derleyici, **_Finally** ile _try arasında ayrım yapamıyor ve **`__finally`** `__try` bir parametre **_try** olarak [__identifier](../../extensions/identifier-cpp-cli.md)geçirildi. Aynı programda her ikisi de tanımlayıcı olarak kullanmayı denememelisiniz, çünkü bu bir [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) hatasına neden olur.

Aşağıdaki örnek C4932 oluşturur:

```cpp
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```
