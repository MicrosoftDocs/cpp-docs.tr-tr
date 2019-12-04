---
title: Derleyici hatası C3507
ms.date: 11/04/2016
f1_keywords:
- C3507
helpviewer_keywords:
- C3507
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
ms.openlocfilehash: 848536e0808d7d6a82ef387e0ca9c64b68ad0007
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753802"
---
# <a name="compiler-error-c3507"></a>Derleyici hatası C3507

bir ProgID en fazla 39 karakter ' ID ' içerebilir; ya da '. ' dışında herhangi bir noktalama işareti içeremez. ya da bir basamakla başlayın

[ProgID](../../windows/progid.md) özniteliğinde, gerçekleştirebileceğiniz değerler üzerinde kısıtlamalar vardır.

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
