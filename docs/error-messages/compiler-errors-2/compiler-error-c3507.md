---
title: Derleyici hatası C3507
ms.date: 11/04/2016
f1_keywords:
- C3507
helpviewer_keywords:
- C3507
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
ms.openlocfilehash: a38efcc0d74bbea0e0bf767cb9e5a11561ab4fb8
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507122"
---
# <a name="compiler-error-c3507"></a>Derleyici hatası C3507

bir ProgID en fazla 39 karakter ' ID ' içerebilir; ya da '. ' dışında herhangi bir noktalama işareti içeremez. ya da bir basamakla başlayın

[ProgID](../../windows/attributes/progid.md) özniteliğinde, gerçekleştirebileceğiniz değerler üzerinde kısıtlamalar vardır.

Aşağıdaki örnek C3507 oluşturur:

```cpp
// C3507.cpp
[module(name="x")];
[
coclass,
progid("0123456789012345678901234567890123456789"),
uuid("00000000-0000-0000-0000-000000000001") // C3507 expected
]
struct CMyStruct {
};
int main() {
}
```
