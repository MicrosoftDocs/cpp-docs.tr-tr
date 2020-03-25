---
title: Derleyici Uyarısı (düzey 1) C4075
ms.date: 11/04/2016
f1_keywords:
- C4075
helpviewer_keywords:
- C4075
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
ms.openlocfilehash: f69d91ee9335201029d6b566b7987df8c267f82b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200232"
---
# <a name="compiler-warning-level-1-c4075"></a>Derleyici Uyarısı (düzey 1) C4075

Tanınmayan başlatma alanına başlatıcılar yerleştirildi

Bir [#pragma init_seg](../../preprocessor/init-seg.md) tanınmayan bir bölüm adı kullanır. Derleyici **pragma** komutunu yoksayar.

Aşağıdaki örnek C4075 oluşturur:

```cpp
// C4075.cpp
// compile with: /W1
#pragma init_seg("mysegg")   // C4075

// try..
// #pragma init_seg(user)

int main() {
}
```
