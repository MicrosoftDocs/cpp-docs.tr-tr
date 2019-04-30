---
title: Derleyici Uyarısı (düzey 1) C4926
ms.date: 11/04/2016
f1_keywords:
- C4926
helpviewer_keywords:
- C4926
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
ms.openlocfilehash: 839d0b8ffad947e7031ca618b255588f54b82770
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393473"
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