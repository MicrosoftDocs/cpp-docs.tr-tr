---
title: Derleyici Uyarısı (Düzey 3) C4073
ms.date: 11/04/2016
f1_keywords:
- C4073
helpviewer_keywords:
- C4073
ms.assetid: 50081a6e-6acd-45ff-8484-9b1ea926cc5c
ms.openlocfilehash: db39f76f9bfdd46c300ea6e3738a63b636fe0a03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429876"
---
# <a name="compiler-warning-level-3-c4073"></a>Derleyici Uyarısı (Düzey 3) C4073

Kitaplığın başlatma alanına başlatıcılar yerleştirildi

Üçüncü taraf kitaplığı geliştiriciler tarafından belirtilen kitaplığın başlatma alanına kullanmalıdır yalnızca [#pragma init_seg](../../preprocessor/init-seg.md). Aşağıdaki örnek, C4073 oluşturur:

```
// C4073.cpp
// compile with: /W3
#pragma init_seg(lib)   // C4073

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```