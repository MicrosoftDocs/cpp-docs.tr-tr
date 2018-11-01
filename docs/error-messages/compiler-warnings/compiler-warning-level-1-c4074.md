---
title: Derleyici Uyarısı (düzey 1) C4074
ms.date: 11/04/2016
f1_keywords:
- C4074
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
ms.openlocfilehash: d9b0259e95198396d8c34ca43781045248e22ad9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665575"
---
# <a name="compiler-warning-level-1-c4074"></a>Derleyici Uyarısı (düzey 1) C4074

Derleyici için ayrılmış başlatma alanına başlatıcılar yerleştirildi

Tarafından belirtilen derleyici başlatma alanına [#pragma init_seg](../../preprocessor/init-seg.md), Microsoft tarafından ayrılmış. Bu alandaki kodu önce C çalışma zamanı kitaplığı başlatma çalıştırılabilir.

Aşağıdaki örnek, C4074 oluşturur:

```
// C4074.cpp
// compile with: /W1
#pragma init_seg( compiler )   // C4074

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```