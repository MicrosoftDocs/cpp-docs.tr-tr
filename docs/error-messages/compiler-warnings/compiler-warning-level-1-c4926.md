---
title: Derleyici Uyarısı (düzey 1) C4926
ms.date: 11/04/2016
f1_keywords:
- C4926
helpviewer_keywords:
- C4926
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
ms.openlocfilehash: a68e251209cb9664552b4324de108f2cf7ce3f37
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74050210"
---
# <a name="compiler-warning-level-1-c4926"></a>Derleyici Uyarısı (düzey 1) C4926

' tanımlayıcı ': simge zaten tanımlandı: öznitelikler yoksayıldı

İleri bildirim bulundu, ancak aynı ada sahip öznitelikli bir yapı zaten var. İleri bildiriminin öznitelikleri yok sayılır.

Aşağıdaki örnek C4926 oluşturur:

```cpp
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